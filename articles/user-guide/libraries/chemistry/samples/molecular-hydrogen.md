---
title: Få beräkningar av energinivå
description: 'Gå igenom ett exempel :::no-loc(Q#)::: program som beräknar energi nivå värden för molekyl väte.'
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 81fba0c52c854d61f9143659795fb4d3c3cee8b9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691526"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="bd139-103">Få beräkningar av energinivå</span><span class="sxs-lookup"><span data-stu-id="bd139-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="bd139-104">Att uppskatta värdena för energi nivåer är ett av de viktigaste programmen i Quantum kemi.</span><span class="sxs-lookup"><span data-stu-id="bd139-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="bd139-105">Den här artikeln beskriver hur du kan utföra detta för det kanoniska exemplet på molekylen väte.</span><span class="sxs-lookup"><span data-stu-id="bd139-105">This article outlines how you can perform this for the canonical example of molecular hydrogen.</span></span> <span data-ttu-id="bd139-106">Exemplet som refereras i det här avsnittet finns [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) i databasen för kemi-exempel.</span><span class="sxs-lookup"><span data-stu-id="bd139-106">The sample referenced in this section is [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) in the chemistry samples repository.</span></span> <span data-ttu-id="bd139-107">Ett mer visuellt exempel som ritar utdata är [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="bd139-107">A more visual example that plots the output is the [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demo.</span></span>

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a><span data-ttu-id="bd139-108">Beräkna energi värden för molekyl väte</span><span class="sxs-lookup"><span data-stu-id="bd139-108">Estimating the energy values of molecular hydrogen</span></span>

<span data-ttu-id="bd139-109">Det första steget är att skapa Hamiltonian som representerar molekylen väte.</span><span class="sxs-lookup"><span data-stu-id="bd139-109">The first step is to construct the Hamiltonian representing molecular hydrogen.</span></span> <span data-ttu-id="bd139-110">Även om du kan skapa detta med NWChem-verktyget för det kortfattat lägger det här exemplet till Hamiltonian-termerna manuellt.</span><span class="sxs-lookup"><span data-stu-id="bd139-110">Although you can construct this using the NWChem tool, for brevity, this sample adds the Hamiltonian terms manually.</span></span>

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

    // Initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

<span data-ttu-id="bd139-111">Att simulera Hamiltonian kräver att fermion-operatörerna konverteras till qubit-operatörer.</span><span class="sxs-lookup"><span data-stu-id="bd139-111">Simulating the Hamiltonian requires converting the fermion operators to qubit operators.</span></span> <span data-ttu-id="bd139-112">Den här konverteringen utförs genom Jordan-Wigner Encoding enligt följande:</span><span class="sxs-lookup"><span data-stu-id="bd139-112">This conversion is performed through the Jordan-Wigner encoding as follows:</span></span>

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // You also need to create an input quantum state to this Hamiltonian.
    // Use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the :::no-loc(Q#)::: operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

<span data-ttu-id="bd139-113">Sedan skickar du `qSharpData` , som representerar Hamiltonian, till `TrotterStepOracle` funktionen.</span><span class="sxs-lookup"><span data-stu-id="bd139-113">Next, pass `qSharpData`, which represents the Hamiltonian, to the `TrotterStepOracle` function.</span></span> <span data-ttu-id="bd139-114">`TrotterStepOracle` Returnerar en Quantum-åtgärd som uppskattar real tids utvecklingen av Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="bd139-114">`TrotterStepOracle` returns a quantum operation that approximates the real-time evolution of the Hamiltonian.</span></span> <span data-ttu-id="bd139-115">Mer information finns i [simulera Hamiltonian Dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span><span class="sxs-lookup"><span data-stu-id="bd139-115">For more information, see [Simulating Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

<span data-ttu-id="bd139-116">Nu kan du använda standard bibliotekets [algoritmer för fas uppskattning](xref:microsoft.quantum.libraries.characterization) för att lära dig om Energis av mark tillstånd med föregående simulering.</span><span class="sxs-lookup"><span data-stu-id="bd139-116">At this point, you can use the standard library's [phase estimation algorithms](xref:microsoft.quantum.libraries.characterization) to learn the ground state energy using the previous simulation.</span></span> <span data-ttu-id="bd139-117">Detta kräver att du förbereder en utmärkt uppskattning till Quantum-jordens tillstånd.</span><span class="sxs-lookup"><span data-stu-id="bd139-117">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="bd139-118">Förslag på sådana ungefärliger finns i [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schemat.</span><span class="sxs-lookup"><span data-stu-id="bd139-118">Suggestions for such approximations are provided in the [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema.</span></span> <span data-ttu-id="bd139-119">Men det finns inga förslag, standard metoden lägger till ett antal `hamiltonian.NElectrons` electrons för att greedily minimera den diagonala en Electron-period Energies.</span><span class="sxs-lookup"><span data-stu-id="bd139-119">However, absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="bd139-120">Fas uppskattnings funktionerna och åtgärderna finns i DocFX-notation i namn området [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization) .</span><span class="sxs-lookup"><span data-stu-id="bd139-120">The phase estimation functions and operations are provided in DocFX notation in the [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization) namespace.</span></span>

<span data-ttu-id="bd139-121">Följande kodfragment visar hur real tids utvecklingen av kemi-utdata från kemi Simulator Library integreras med uppskattning av Quantum-fasen.</span><span class="sxs-lookup"><span data-stu-id="bd139-121">The following snippet shows how the real-time evolution output by the chemistry simulation library integrates with quantum phase estimation.</span></span>

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // Using a Product formula, also known as `Trotterization`, to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined here.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // Using the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // Now, obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // Return both the estimated phase and the estimated energy.
    return (estPhase, estEnergy);
}
```

<span data-ttu-id="bd139-122">Du kan nu anropa :::no-loc(Q#)::: koden från värd programmet.</span><span class="sxs-lookup"><span data-stu-id="bd139-122">You can now invoke the :::no-loc(Q#)::: code from the host program.</span></span> <span data-ttu-id="bd139-123">Följande C#-kod skapar en komplett-tillstånds Simulator och kör `GetEnergyByTrotterization` för att hämta jord tillstånds energi.</span><span class="sxs-lookup"><span data-stu-id="bd139-123">The following C# code creates a full-state simulator and runs `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

```csharp
using (var qsim = new QuantumSimulator())
{
    // Specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // Specify the step size of the simulated time evolution. The step size needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

<span data-ttu-id="bd139-124">Åtgärden returnerar två parametrar:</span><span class="sxs-lookup"><span data-stu-id="bd139-124">The operation returns two parameters:</span></span> 

- <span data-ttu-id="bd139-125">`energyEst` är beräkningen av jord stats energins energi och bör ligga nära `-1.137` i genomsnitt.</span><span class="sxs-lookup"><span data-stu-id="bd139-125">`energyEst` is the estimate of the ground state energy and should be close to `-1.137` on average.</span></span> 
- <span data-ttu-id="bd139-126">`phaseEst` är den råa fasen som returneras av algoritmen för fas uppskattning.</span><span class="sxs-lookup"><span data-stu-id="bd139-126">`phaseEst` is the raw phase returned by the phase estimation algorithm.</span></span> <span data-ttu-id="bd139-127">Detta är användbart för att diagnostisera alias när det inträffar på grund av ett `trotterStep` värde som är för stort.</span><span class="sxs-lookup"><span data-stu-id="bd139-127">This useful for diagnosing aliasing when it occurs due to a `trotterStep` value that is too large.</span></span>
