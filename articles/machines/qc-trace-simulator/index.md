---
title: Spårningssimulator för kvantdator | Microsoft Docs
description: Översikt över spårningssimulator för kvantdator
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 7fd9d1fa4fb3c5dd216d846038abd40454ece2e8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035125"
---
# <a name="quantum-trace-simulator"></a>Spårningssimulator för kvantdator

Microsofts spårningssimulator för kvantdatorer kör ett kvantprogram utan att egentligen simulera tillståndet i en kvantdator.  Det innebär att spårningssimulatorn kan köra kvantprogram som använder tusentals kvantbitar.  Det är användbart av två viktiga orsaker: 

* Vid felsökning av klassisk kod som ingår i ett kvantprogram. 
* Vid beräkning av vilka resurser som krävs för att köra en specifik instans av ett kvantprogram på en kvantdator.

Spårningssimulatorn måste erhålla ytterligare information från användaren när mätningarna ska utföras. Mer information om detta finns i avsnittet [Ange sannolikheten för mätresultatet](#providing-the-probability-of-measurement-outcomes). 

## <a name="providing-the-probability-of-measurement-outcomes"></a>Ange sannolikheten för mätresultatet

Det finns två typer av mått som syns i kvantalgoritmer. Den första typen används när användaren vanligtvis känner till sannolikheten för resultatet. I detta fall kan användaren skriva <xref:microsoft.quantum.primitive.assertprob> från namnområdet <xref:microsoft.quantum.primitive> för att visa att kunskapen finns. Följande exempel illustrerar detta:

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

När spårningssimulatorn kör `AssertProb` kommer den registrera att mätning av `PauliZ` i `source` och `ancilla` bör få ett resultat på `Zero` med sannolikheten 0,5. När simulatorn senare kör `M` kommer den att hitta de registrerade värdena för resultatets sannolikhet och `M` returnerar `Zero` eller `One` med sannolikheten 0,5. När samma kod körs på en simulator som håller koll på kvanttillståndet, kontrollerar simulatorn att de angivna sannolikheterna i `AssertProb` är korrekta.

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a>Köra ditt program med spårningssimulatorn för kvantdatorer 

Spårningssimulatorn för kvantdatorer kan betraktas som en annan måldator. C#-drivrutinen för att använda den liknar den som finns för andra kvantsimulatorer: 

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Observera att om det finns minst en mätning som inte är kommenterad med `AssertProb`, kommer simulatorn att utlösa `UnconstrainedMeasurementException` från namnområdet `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`. Mer information finns i API-dokumentationen om [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException).

Förutom att köra kvantprogram levereras spårningssimulatorn med fem komponenter som identifierar buggar i program och utför uppskattningar av kvantprogramresurser: 

* [Kontroll av distinkta indata](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [Upphävd användningskontroll för kvantbitar](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [Räknare för primitiva åtgärder](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [Räknare för kretsdjup](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [Räknare för kretsbredd](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

Var och en av dessa komponenter kan aktiveras genom att lämpliga flaggor anges i `QCTraceSimulatorConfiguration`. Mer information om hur du använder de olika komponenterna finns i tillhörande referensfiler. Mer information finns i API-dokumentationen om [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="see-also"></a>Se även
C#-referens till [spårningssimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) för kvantdator 

