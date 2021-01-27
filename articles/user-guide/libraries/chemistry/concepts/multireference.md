---
title: Korrelerade vågfunktioner
description: Lär dig om dynamiska och icke-dynamiska korrelationer i wavefunctions med Microsoft Quantum kemi-biblioteket.
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.multireference
no-loc:
- Q#
- $$v
ms.openlocfilehash: ab3d90d79c7c14a1ef5b3aa833df49be186f3dd7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856277"
---
# <a name="correlated-wavefunctions"></a><span data-ttu-id="9d3fd-103">Korrelerade vågfunktioner</span><span class="sxs-lookup"><span data-stu-id="9d3fd-103">Correlated wavefunctions</span></span>

<span data-ttu-id="9d3fd-104">För många system, särskilt de nära jämvikts geometrin, ger [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) teori en kvalitativ beskrivning av molekyl egenskaper genom ett engångs referens tillstånd.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-104">For many systems, particularly those near the equilibrium geometry, [Hartree–Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) theory provides a qualitative description of molecular properties through a single-determinant reference state.</span></span> <span data-ttu-id="9d3fd-105">Men för att uppnå kvantitativ noggrannhet måste det också ta hänsyn till korrelations effekter.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-105">However, in order to achieve quantitative accuracy, one must also consider correlation effects.</span></span> 

<span data-ttu-id="9d3fd-106">I det här sammanhanget är det viktigt att dinstinguish mellan dynamiska och icke-dynamiska korrelationer.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-106">In this context, it is important to dinstinguish between dynamic and non-dynamic correlations.</span></span>
<span data-ttu-id="9d3fd-107">Det uppstår dynamiska korrelationer från tendensen av electrons för att hålla isär, till exempel på grund av en interelektronisk drivning.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-107">Dynamical correlations arise from the tendency of electrons to stay apart, such as due to interelectronic repulsion.</span></span> <span data-ttu-id="9d3fd-108">Den här funktionen kan utformas genom att man överväger excitations av electrons.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-108">This effect can be modelled by considering excitations of electrons out of the reference state.</span></span> <span data-ttu-id="9d3fd-109">Icke-dynamiska korrelationer uppstår när wavefunction är dominerats av två eller flera konfigurationer i Zeroth-ordning, även om du bara vill uppnå en kvalitativ beskrivning av systemet.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-109">Non-dynamic correlations arise when the wavefunction is dominated by two or more configurations at zeroth order, even to achieve only a qualitative description of the system.</span></span>
<span data-ttu-id="9d3fd-110">Detta kräver en överplacering av Determinant och är ett exempel på en wavefunction med multireferens.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-110">This necessitates a superposition of determinants and is an example of a multireference wavefunction.</span></span>

<span data-ttu-id="9d3fd-111">Kemi-biblioteket är ett sätt att ange en Zeroth order-wavefunction för ett multireferens-problem som en överplacering av Determinant.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-111">The chemistry library provides a way to specify a zeroth order wavefunction for the multireference problem as a superposition of determinants.</span></span> <span data-ttu-id="9d3fd-112">Den här metoden, som vi kallar sparse multireference wavefunctions, är effektiv när bara några få komponenter räcker för att ange överplacering.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-112">This approach, which we call sparse multireference wavefunctions, is effective when only a few components suffice to specify the superposition.</span></span> <span data-ttu-id="9d3fd-113">Biblioteket innehåller också en metod för att inkludera dynamiska korrelationer ovanpå en engångs referens via den generaliserade enhetliga kluster ansatz.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-113">The library also provides a method to include dynamic correlations on top of a single-determinant reference via the generalized unitary coupled-cluster ansatz.</span></span> <span data-ttu-id="9d3fd-114">Dessutom konstrueras även Quantum-kretsar som genererar dessa tillstånd på en Quantum-dator.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-114">Furthermore, it also constructs quantum circuits that generate these states on a quantum computer.</span></span> <span data-ttu-id="9d3fd-115">Dessa tillstånd kan anges i Broombridge- [schemat](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)och vi tillhandahåller även funktionen för att manuellt ange dessa tillstånd via kemi-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-115">These states may be specified in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), and we also provide the functionality to manually specify these states through the chemistry library.</span></span>

## <a name="sparse-multi-reference-wavefunction"></a><span data-ttu-id="9d3fd-116">Wavefunction för sparse-flera referenser</span><span class="sxs-lookup"><span data-stu-id="9d3fd-116">Sparse multi-reference wavefunction</span></span>
<span data-ttu-id="9d3fd-117">En \ket{\ för flera referenser $ psi_ {\rm {MCSCF}}} $ kan anges explicit som en linjär kombination av $N $-Electron Slater determininants.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-117">A multi-reference state $\ket{\psi_{\rm {MCSCF}}}$ may be specified explicitly as a linear combination of $N$-electron Slater determininants.</span></span>
<span data-ttu-id="9d3fd-118">\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots a ^ \ dagger_ {i_N} \ket {0} .</span><span class="sxs-lookup"><span data-stu-id="9d3fd-118">\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket{0}.</span></span>
<span data-ttu-id="9d3fd-119">\end{align} t. ex. State $ \propto (0,1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ kan anges i kemi-biblioteket på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-119">\end{align} For example, the state $\propto(0.1 a^\dagger_1a^\dagger_2a^\dagger_6 - 0.2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ may be specified in the chemistry library as follows.</span></span>
```csharp
// Create a list of tuples where the first item of each 
// tuple are indices to the creation operators acting on the
// vacuum state, and the second item is the coefficient
// of that basis state.
var superposition = new[] {
    (new[] {1, 2, 6}, 0.1),
    (new[] {2, 1, 5}, -0.2) };

// Create a fermion wavefunction object that represents the superposition.
var wavefunction = new FermionWavefunction<int>(superposition);
```
<span data-ttu-id="9d3fd-120">Den här explicita representationen av superpositions komponenterna är effektiv när bara några få komponenter behöver anges.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-120">This explicit representation of the superposition components is effective when only a few components need to be specified.</span></span> <span data-ttu-id="9d3fd-121">Du bör undvika att använda den här representationen när många komponenter krävs för att korrekt kunna avbilda det önskade läget.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-121">One should avoid using this representation when many components are required to accurately capture the desired state.</span></span> <span data-ttu-id="9d3fd-122">Anledningen är att den här gaten är en Quantum-krets som förbereder det här läget på en Quantum-dator, som skalas minst linjärt med antalet superpositions komponenter och som är mest kvadratiskt med en-norm för amplituderna superposition.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-122">The reason for this is the gate cost of quantum circuit that prepares this state on a quantum computer, which scales at least linearly with the number of superposition components, and at most quadratically with the one-norm of the superposition amplitudes.</span></span>

## <a name="unitary-coupled-cluster-wavefunction"></a><span data-ttu-id="9d3fd-123">Enhetligt kluster wavefunction</span><span class="sxs-lookup"><span data-stu-id="9d3fd-123">Unitary coupled-cluster wavefunction</span></span>
<span data-ttu-id="9d3fd-124">Det är också möjligt att ange en enhetlig, fristående kluster wavefunction $ \ket{\ psi_ {\rm {UCC}}} $ med chemistery-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-124">It is also possible to specify a unitary coupled-cluster wavefunction $\ket{\psi_{\rm {UCC}}}$ using the chemistery library.</span></span> <span data-ttu-id="9d3fd-125">I den här situationen har vi ett engångs referens tillstånd, t. ex. $ \ket{\ psi_ {\rm{SCF}}} $.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-125">In this situation, we have a single-determinant reference state, say, $\ket{\psi_{\rm{SCF}}}$.</span></span> <span data-ttu-id="9d3fd-126">Komponenterna i den enhetliga kluster wavefunction anges sedan som implicit genom en enhetlig operatör som agerar i ett referens tillstånd.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-126">The components of the unitary coupled-cluster wavefunction are then specified implicity through a unitary operator acting on a reference state.</span></span>
<span data-ttu-id="9d3fd-127">Den här enhetliga operatorn skrivs vanligt vis som $e ^ {T-T ^ \dagger} $, där $T-T ^ \dagger $ är den Hermitian kluster operatorn.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-127">This unitary operator is commonly written as $e^{T-T^\dagger}$, where $T-T^\dagger$ is the anti-Hermitian cluster operator.</span></span> <span data-ttu-id="9d3fd-128">Därför \begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-128">Thus \begin{align} \ket{\psi_{\rm {UCC}}} = e^{T-T^\dagger}\ket{\psi_{\rm{SCF}}}.</span></span>
<span data-ttu-id="9d3fd-129">\end{align}</span><span class="sxs-lookup"><span data-stu-id="9d3fd-129">\end{align}</span></span>

<span data-ttu-id="9d3fd-130">Det är också vanligt att dela upp kluster operatorn $T = T_1 + T_2 + \cdots $ i delar, där varje del $T _j $ innehåller $j $-Body-villkor.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-130">It is also common to split the cluster operator $T = T_1 + T_2 + \cdots$ into parts, where each part $T_j$ contains $j$-body terms.</span></span> <span data-ttu-id="9d3fd-131">I generaliserad kluster teori är Singles (Enbody Cluster-operatören) av formatet \begin{align} T_1 = \ sum_ {PQ} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}</span><span class="sxs-lookup"><span data-stu-id="9d3fd-131">In generalized coupled-cluster theory, the one-body cluster operator (singles) is of the form \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span></span>

<span data-ttu-id="9d3fd-132">och två huvud kluster operatörer (dubbla) har formatet \begin{align} T_2 = \ sum_ {PQRS} T ^ {PQ} _ {RS} a ^ \ dagger_p a ^ \ dagger_q a_r a_s.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-132">and two-body cluster operator (doubles) is of the form \begin{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span></span>
<span data-ttu-id="9d3fd-133">\end{align}</span><span class="sxs-lookup"><span data-stu-id="9d3fd-133">\end{align}</span></span>

<span data-ttu-id="9d3fd-134">Högre ordning (tredubbla, fyr dubbels osv.) är möjliga, men stöds för närvarande inte av kemi-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-134">Higher-order terms (triples, quadruples, etc.) are possible, but not currently supported by the chemistry library.</span></span>

<span data-ttu-id="9d3fd-135">Låt säga att $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} $ och låt $T = 0,123 a ^ \ dagger_0 A_1 + 0,456 a ^ \ dagger_0a ^ \ dagger_3 a_1 a_2-0,789 a ^ \ dagger_3a ^ \ dagger_2 A_1 a_0 $.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-135">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket{0}$, and let $T= 0.123 a^\dagger_0 a_1 + 0.456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0.789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span></span> <span data-ttu-id="9d3fd-136">Sedan instansieras det här läget i kemi-biblioteket på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-136">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { 1, 2 };

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {0, 1}, 0.123),
    (new [] {0, 3, 1, 2}, 0.456),
    (new [] {3, 2, 1, 0}, 0.789)
};

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunction = new FermionWavefunction<int>(reference, clusterOperator);
```

<span data-ttu-id="9d3fd-137">Rotations convervation kan göras explicit genom att i stället ange `SpinOrbital` index i stället för heltals index.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-137">Spin convervation may be made explicit by instead specifying `SpinOrbital` indices instead of integer indices.</span></span> <span data-ttu-id="9d3fd-138">Låt säga att $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} a ^ \ dagger_ {2, \downarrow}\ket {0} $ och låt $T = 0,123 a ^ \ dagger_ {0, \uparrow} a_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} a_ {1, \uparrow} a_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ convserving.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-138">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, and let $T= 0.123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0.456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0.789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ be spin convserving.</span></span> <span data-ttu-id="9d3fd-139">Sedan instansieras det här läget i kemi-biblioteket på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-139">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {(0, Spin.u), (1, Spin.u)}, 0.123),
    (new [] {(0, Spin.u), (3, Spin.d), (1, Spin.u), (2, Spin.d)}, 0.456),
    (new [] {(3, Spin.u), (2, Spin.u), (1, Spin.u), (0, Spin.u)}, 0.789)
}.Select(o => (o.Item1.ToSpinOrbitals(), o.Item2);

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(reference, clusterOperator);

// Convert the wavefunction indexed by spin-orbitals to one indexed
// by integers
var wavefunctionInteger = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="9d3fd-140">Vi tillhandahåller också en bekvämlighets funktion som räknar upp över alla konversation kluster operatörer som Annihilate endast upptagna varv-och glädjer-funktioner.</span><span class="sxs-lookup"><span data-stu-id="9d3fd-140">We also provide a convenience function that enumerates over all spin-conversing cluster operators that annihilate only occupied spin-orbitals and excite to only unoccupied spin-orbitals.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Generate all spin-conversing excitations from spin-orbitals 
// occupied by the reference state to virtual orbitals.
var generatedExcitations = reference.CreateAllUCCSDSingletExcitations(nOrbitals: 3).Excitations;

// This is the list of expected spin-consvering excitations
var expectedExcitations = new[]
{
    new []{ (0, Spin.u), (1,Spin.u)},
    new []{ (2, Spin.u), (1,Spin.u)},
    new []{ (0, Spin.d), (2,Spin.d)},
    new []{ (1, Spin.d), (2,Spin.d)},
    new []{ (0, Spin.u), (0, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.u), (1, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)},
    new []{ (1, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)}
}.Select(o => new IndexOrderedSequence<SpinOrbital>(o.ToLadderSequence()));

// The following two assertions are true, and verify that the generated 
// excitations exactly match the expected excitations.
var bool0 = generatedExcitations.Keys.All(expectedExcitations.Contains);
var bool1 = generatedExcitations.Count() == expectedExcitations.Count();
```
