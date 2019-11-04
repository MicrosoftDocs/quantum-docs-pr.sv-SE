---
title: Erhåller energi nivå uppskattningar | Microsoft Docs
description: Hämta dokument på energi nivå uppskattningar
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 0fd457b152083af364d924502c18bc0813e34b83
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442583"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="99e33-103">Få beräkningar av energinivå</span><span class="sxs-lookup"><span data-stu-id="99e33-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="99e33-104">Att uppskatta värdena för energi nivåer är ett av de viktigaste programmen i Quantum kemi.</span><span class="sxs-lookup"><span data-stu-id="99e33-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="99e33-105">Här kan vi disponera hur detta kan utföras för det kanoniska exemplet på molekylen väte.</span><span class="sxs-lookup"><span data-stu-id="99e33-105">Here, we outline how this may be performed for the canonical example of molecular Hydrogen.</span></span> <span data-ttu-id="99e33-106">Exemplet som refereras i det här avsnittet är `MolecularHydrogen` i databasen för kemi-exempel.</span><span class="sxs-lookup"><span data-stu-id="99e33-106">The sample referenced in this section is `MolecularHydrogen` in the chemistry samples repository.</span></span> <span data-ttu-id="99e33-107">Ett mer visuellt exempel som ritar utdata är `MolecularHydrogenGUI` demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="99e33-107">A more visual example that plots the output is the `MolecularHydrogenGUI` demo.</span></span>

<span data-ttu-id="99e33-108">Vårt första steg är att skapa Hamiltonian som representerar molekylen väte.</span><span class="sxs-lookup"><span data-stu-id="99e33-108">Our first step is to construct the Hamiltonian representing molecular Hydrogen.</span></span> <span data-ttu-id="99e33-109">Även om detta kan konstrueras via NWChem-verktyget lägger vi manuellt till Hamiltonian-villkor för det kortfattat i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="99e33-109">Though this can be constructed through the NWChem tool, we manually add Hamiltonian terms for brevity in this sample.</span></span>

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

<span data-ttu-id="99e33-110">Att simulera Hamiltonian kräver att vi konverterar fermion-operatörerna till qubit-operatörer.</span><span class="sxs-lookup"><span data-stu-id="99e33-110">Simulating the Hamiltonian requires us to convert the fermion operators to qubit operators.</span></span> <span data-ttu-id="99e33-111">Den här konverteringen utförs via Wigner-kodningen i Jordanien på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="99e33-111">This conversion is performed through the Jordan-Wigner encoding as follows.</span></span>

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

<span data-ttu-id="99e33-112">Vi skickar nu `qSharpData` som representerar Hamiltonian till funktionen `TrotterStepOracle` i [simulera Hamiltonian Dynamics](xref:microsoft.quantum.libraries.standard.algorithms).</span><span class="sxs-lookup"><span data-stu-id="99e33-112">We now pass the `qSharpData` representing the Hamiltonian to the `TrotterStepOracle` function in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms).</span></span> <span data-ttu-id="99e33-113">`TrotterStepOracle` returnerar en Quantum-åtgärd som uppskattar den real tids utvecklingen för Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="99e33-113">`TrotterStepOracle` returns a quantum operation that approximates the real time-evolution of the Hamiltonian.</span></span>

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

<span data-ttu-id="99e33-114">Vi kan nu använda standard bibliotekets algoritmer för fas uppskattning för att lära dig om energi förbrukningen med hjälp av ovanstående simulering.</span><span class="sxs-lookup"><span data-stu-id="99e33-114">We can now use the standard library's phase estimation algorithms to learn the ground state energy using the above simulation.</span></span> <span data-ttu-id="99e33-115">Detta kräver att du förbereder en utmärkt uppskattning till Quantum-jordens tillstånd.</span><span class="sxs-lookup"><span data-stu-id="99e33-115">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="99e33-116">Förslag på sådana uppskattningar finns i `Broombridge`-schemat, men utanför dessa förslag lägger standard metoden till ett antal `hamiltonian.NElectrons` electrons till greedily minimerar den diagonala en Electron-Energies.</span><span class="sxs-lookup"><span data-stu-id="99e33-116">Suggestions for such approximations are provided in the `Broombridge` schema, but absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to  greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="99e33-117">Fas beräknings funktionerna och åtgärderna finns i [namn området Microsoft. Quantum. karakterisering](xref:microsoft.quantum.characterization in DocFX notation).</span><span class="sxs-lookup"><span data-stu-id="99e33-117">The phase estimation functions and operations are located in the [Microsoft.Quantum.Characterization namespace](xref:microsoft.quantum.characterization in DocFX notation).</span></span>

<span data-ttu-id="99e33-118">Följande kodfragment visar hur real tids utvecklings resultatet av kemi Simulator Library kan integreras med en uppskattning av Quantum-fasen.</span><span class="sxs-lookup"><span data-stu-id="99e33-118">The following snippet shows how the real time-evolution output by the chemistry simulation library may be integrated with quantum phase estimation.</span></span>

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

<span data-ttu-id="99e33-119">Den här Q #-koden kan nu anropas från driv rutins programmet.</span><span class="sxs-lookup"><span data-stu-id="99e33-119">This Q# code may now be invoke from the driver program.</span></span> <span data-ttu-id="99e33-120">I följande skapar vi en komplett-tillstånds Simulator och kör `GetEnergyByTrotterization` för att hämta jord tillstånds energi.</span><span class="sxs-lookup"><span data-stu-id="99e33-120">In the following, we create a full-state simulator and run `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

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

<span data-ttu-id="99e33-121">Observera att två parametrar returneras.</span><span class="sxs-lookup"><span data-stu-id="99e33-121">Note that two parameters are returned.</span></span> <span data-ttu-id="99e33-122">`energyEst` är en uppskattning av jord stats energins energi och bör vara runt `-1.137` i genomsnitt.</span><span class="sxs-lookup"><span data-stu-id="99e33-122">`energyEst` is the estimate of the ground state energy, and should be around `-1.137` on average.</span></span> <span data-ttu-id="99e33-123">`phaseEst` är den råa fasen som returneras av algoritmen för fas uppskattning och är användbar för att diagnostisera när alias inträffar på grund av en `trotterStep` som är för stor.</span><span class="sxs-lookup"><span data-stu-id="99e33-123">`phaseEst` is the raw phase returned by the phase estimation algorithm, and is useful to diagnose when aliasing occurs due to a `trotterStep` that is too large.</span></span>
