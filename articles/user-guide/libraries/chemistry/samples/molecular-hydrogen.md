---
title: Få beräkningar av energinivå
description: 'Gå igenom ett exempel på ett Q #-program som beräknar energi nivå värden för molekyl väte.'
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 3242d8c6dc6fad2bd99055027dd7ce4ec3510ff4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276058"
---
# <a name="obtaining-energy-level-estimates"></a>Få beräkningar av energinivå
Att uppskatta värdena för energi nivåer är ett av de viktigaste programmen i Quantum kemi. Här kan vi disponera hur detta kan utföras för det kanoniska exemplet på molekylen väte. Exemplet som refereras i det här avsnittet finns `MolecularHydrogen` i databasen för kemi-exempel. Ett mer visuellt exempel som ritar utdata är `MolecularHydrogenGUI` demonstrationen.

Vårt första steg är att skapa Hamiltonian som representerar molekylen väte. Även om detta kan konstrueras via NWChem-verktyget lägger vi manuellt till Hamiltonian-villkor för det kortfattat i det här exemplet.

```csharp
    // These orbital integrals are represented using the OrbitalIntegral
    // data structure.
    var energyOffset = 0.713776188; // This is the coulomb repulsion
    var nElectrons = 2; // Molecular hydrogen has two electrons
    var orbitalIntegrals = new OrbitalIntegral[]
    {
        new OrbitalIntegral(new[] { 0,0 }, -1.252477495),
        new OrbitalIntegral(new[] { 1,1 }, -0.475934275),
        new OrbitalIntegral(new[] { 0,0,0,0 }, 0.674493166),
        new OrbitalIntegral(new[] { 0,1,0,1 }, 0.181287518),
        new OrbitalIntegral(new[] { 0,1,1,0 }, 0.663472101),
        new OrbitalIntegral(new[] { 1,1,1,1 }, 0.697398010),
        // This line adds the identity term.
        new OrbitalIntegral(new int[] { }, energyOffset)
    };

    // We initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

Att simulera Hamiltonian kräver att vi konverterar fermion-operatörerna till qubit-operatörer. Den här konverteringen utförs via Wigner-kodningen i Jordanien på följande sätt.

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // We also need to create an input quantum state to this Hamiltonian.
    // Let us use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Vi skickar nu det `qSharpData` som representerar Hamiltonian till `TrotterStepOracle` funktionen i [simulerade Hamiltonian Dynamics](xref:microsoft.quantum.libraries.standard.algorithms). `TrotterStepOracle`Returnerar en Quantum-åtgärd som uppskattar den real tids utvecklingen för Hamiltonian.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

Vi kan nu använda standard bibliotekets algoritmer för fas uppskattning för att lära dig om energi förbrukningen med hjälp av ovanstående simulering. Detta kräver att du förbereder en utmärkt uppskattning till Quantum-jordens tillstånd. Förslag på sådana uppskattningar finns i `Broombridge` schemat, men utanför de här förslagen är standard metoden ett antal `hamiltonian.NElectrons` electrons som gör att greedily minimerar den diagonala en Electron term Energies. Fas beräknings funktionerna och åtgärderna finns i [namn området Microsoft. Quantum. karakterisering](xref:microsoft.quantum.characterization in DocFX notation).

Följande kodfragment visar hur real tids utvecklings resultatet av kemi Simulator Library kan integreras med en uppskattning av Quantum-fasen.

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined below.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // We use the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // We obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // We return both the estimated phase, and the estimated energy.
    return (estPhase, estEnergy);
}
```

Den här Q #-koden kan nu anropas från driv rutins programmet. I följande skapar vi en komplett-tillstånds Simulator och kör `GetEnergyByTrotterization` för att hämta jord tillstånds energi.

```csharp
using (var qsim = new QuantumSimulator())
{
    // We specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // We specify the step-size of the simulated time-evolution. This needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, let us run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular Hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

Observera att två parametrar returneras. `energyEst`är beräkningen av jord-och energi förbrukningen och bör vara runt `-1.137` om genomsnittet. `phaseEst`är den råa fasen som returneras av algoritmen för fas uppskattning och är användbar för att diagnostisera när alias inträffar på grund av att `trotterStep` det är för stort.
