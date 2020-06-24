---
title: Få resursantal
description: Lär dig hur du erhåller resurs beräkningar med en Quantum trace Simulator.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: 14d0a703a20a801dcee9678a113a33404859a1a9
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275883"
---
# <a name="obtaining-resource-counts"></a>Få resursantal

Kostnaden för att simulera $n $ qubits på klassiska datorer skalas exponentiellt med $n $. Detta begränsar storleken på en Quantum kemi-simulering som vi kan utföra med hela tillstånds simulatorn. För stora instanser av kemi kan vi ändå få värdefull information. Här kan vi se hur resurs kostnader, till exempel antalet T-grindar eller CNOT-grindar, för att simulera kemi kan erhållas på ett automatiserat sätt med hjälp av [spårnings simulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Sådan information informerar oss om att quantum-datorer kan vara tillräckligt stora för att köra dessa Quantum kemi-algoritmer. För referens, se det tillhandahållna `GetGateCount` exemplet.

Låt oss anta att vi redan har en `FermionHamiltonian` instans, t. ex. inläst från Broombridge-schemat som beskrivs i exemplet [inläsnings-från-fil](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) . 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

Syntaxen för att få resurs uppskattningar är nästan identiska för att köra algoritmen i full-State-simulatorn. Vi väljer bara en annan måldator. För resurs uppskattningar räcker det att utvärdera kostnaden för ett enda Trotter-steg eller en Quantum-åtgärd som skapats av Qubitization-tekniken. Standard för att anropa dessa algoritmer är följande.

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

Nu konfigurerar vi spårnings simulatorn för att spåra de resurser vi är intresserade av. I det här fallet räknar vi primitiva Quantum-åtgärder genom `usePrimitiveOperationsCounter` att ange flaggan till `true` . En teknisk information `throwOnUnconstraintMeasurement` ställs in på `false` för att undvika undantag i fall där Q #-koden inte är korrekt försäkrad om sannolikheten för Mät resultat, om sådana utförs.

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

Nu kör vi Quantum-algoritmen från driv rutins programmet på följande sätt.

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```