---
title: Andra kvantifieringsfel
description: Lär dig mer om den andra kvantifieringsfel-metoden för att utforma elektroniska strukturer i Quantum-programmering.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6becd348f7b3957cb60b16bbd5a28228527e1d4c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835816"
---
# <a name="second-quantization"></a><span data-ttu-id="4ab82-103">Andra kvantifieringsfel</span><span class="sxs-lookup"><span data-stu-id="4ab82-103">Second Quantization</span></span>

<span data-ttu-id="4ab82-104">Andra kvantifieringsfel tittar på problemet med elektronisk struktur via en annan lins.</span><span class="sxs-lookup"><span data-stu-id="4ab82-104">Second quantization looks at the problem of electronic structure through a different lens.</span></span>
<span data-ttu-id="4ab82-105">I stället för att tilldela var och en av de $N _e $ electrons till ett särskilt tillstånd (eller orbital), spårar andra kvantifieringsfel varje orbital och lagrar om det finns en Electron som finns på var och en av dem och samtidigt säkerställer egenskaperna för den motsvarande Wave-funktionens symmetri egenskaper automatiskt.</span><span class="sxs-lookup"><span data-stu-id="4ab82-105">Rather than assigning each of the $N_e$ electrons to a specific state (or orbital), second quantization tracks each orbital and stores whether there is an electron present in each of them and at the same time automatically ensures symmetry properties of the corresponding wave function.</span></span>
<span data-ttu-id="4ab82-106">Detta är viktigt eftersom det gör det möjligt att ange Quantum kemi-modeller utan att behöva oroa sig för att symmetrizing ingångs tillstånd (som krävs för Fermions) och även om andra kvantifieringsfel tillåter att sådana modeller simuleras med hjälp av små quantum datorer.</span><span class="sxs-lookup"><span data-stu-id="4ab82-106">This is important because it allows quantum chemistry models to be specified without having to worry about anti-symmetrizing the input state (as is required for fermions) and also because second quantization allows such models to be simulated using small quantum computers.</span></span>

<span data-ttu-id="4ab82-107">Som ett exempel på andra kvantifieringsfel i praktiken antar vi att $ \ psi_0 \cdots \ psi_ {N-1} $ är en orthonormal uppsättning med avstånd för överbanor.</span><span class="sxs-lookup"><span data-stu-id="4ab82-107">As an example of second quantization in action, let's assume that $\psi_0\cdots \psi_{N-1}$ are an orthonormal set of spatial orbitals.</span></span>
<span data-ttu-id="4ab82-108">Dessa insikter väljs för att representera systemet så korrekt som möjligt inom den begränsade bas uppsättningen som beaktas.</span><span class="sxs-lookup"><span data-stu-id="4ab82-108">These orbitals are chosen to represent the system as accurately as possible within the finite basis set considered.</span></span>
<span data-ttu-id="4ab82-109">Ett vanligt exempel på sådana banor är atomiska banor som bildar en eigenbasis för väte-Atomen.</span><span class="sxs-lookup"><span data-stu-id="4ab82-109">A common example of such orbitals are atomic orbitals which form an eigenbasis for the hydrogen atom.</span></span>
<span data-ttu-id="4ab82-110">Eftersom electrons har två varv tillstånd kan två electrons vara Crammed i varje sådan spatiala orbital.</span><span class="sxs-lookup"><span data-stu-id="4ab82-110">Because electrons have two spin states, two electrons can be crammed into each such spatial orbital.</span></span>
<span data-ttu-id="4ab82-111">Det vill säga att giltiga bas tillstånd är av typen $ \ psi_ {0, \uparrow}, \ldots, \ psi_ {N-1, \uparrow}, \ psi_ {0, \downarrow}, \ldots, \ psi_ {N-1, \downarrow} $ där $ \uparrow $ och $ \downarrow $ är etiketter som anger de två eigenstates i rotations graden.</span><span class="sxs-lookup"><span data-stu-id="4ab82-111">That is to say, the valid basis states are of the form $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ where $\uparrow$ and $\downarrow$ are labels that specify the two eigenstates of the spin degree of freedom.</span></span>
<span data-ttu-id="4ab82-112">Det här kombinerade indexet $ (j, \sigma) $ för $ \sigma \in \{ \uparrow, \downarrow \} $ kallas för ett rotations-orbital eftersom det lagrar både spatialdata och rotations graden för frihet.</span><span class="sxs-lookup"><span data-stu-id="4ab82-112">This combined index of $(j,\sigma)$ for $\sigma \in \{\uparrow,\downarrow\}$ is called a spin-orbital because it stores both the spatial as well as the spin degree of freedom.</span></span>
<span data-ttu-id="4ab82-113">I kemi-biblioteket lagras rotations-banor i en `SpinOrbital` data struktur och skapas på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="4ab82-113">In the chemistry library, spin-orbitals are stored in a `SpinOrbital` data structure, and are created as follows.</span></span>

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

<span data-ttu-id="4ab82-114">Det innebär att vi kan formellt tänka på grund för både rotations-och rums delen av vågen som $ \ psi_ {0} \cdots \ psi_ {2n-1} $ där var och en av indexen nu är en uppräkning av en $ (j, \sigma) $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-114">This means that we can formally think of the basis for both the spin and spatial part of the wave function as $\psi_{0} \cdots \psi_{2N-1}$ where each of the indices now is an enumeration of a $(j,\sigma)$.</span></span>
<span data-ttu-id="4ab82-115">En möjlig uppräkning är $g (j, \sigma) = j + N\sigma $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-115">One possible enumeration is $g(j,\sigma) = j+N\sigma'$.</span></span>
<span data-ttu-id="4ab82-116">En annan möjlig uppräkning är $h (j, \sigma) = 2 \* j + \sigma $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-116">Another possible enumeration is $h(j,\sigma) = 2\*j + \sigma$.</span></span>
<span data-ttu-id="4ab82-117">Quantum kemi-biblioteket kan använda dessa konventioner och rotations banaarna i en sådan kodning kan instansieras på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="4ab82-117">The quantum chemistry library can use these conventions, and the spin-orbitals in such an encoding can be instantiated as follows.</span></span>

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

<span data-ttu-id="4ab82-118">För fermionic-system förhindrar Pauli uteslutnings principen att fler än en Electron förekommer i en rotations-orbital på samma tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="4ab82-118">For fermionic systems, the Pauli exclusion principle prevents more than one electron from being present in any spin-orbital at the same time.</span></span>
<span data-ttu-id="4ab82-119">Det innebär att vi kan skriva de två juridiska tillstånden för $ \ psi_1 $ som \begin{Equation} \ psi_1 \rightarrow \begin{Cases} \ket {0} _1 & \text{IF $ \ psi_1 $ inte är upptagna,} </span><span class="sxs-lookup"><span data-stu-id="4ab82-119">This means that we can write the two legal states for $\psi_1$ as \begin{equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $\psi_1$ is not occupied,} </span></span>\\\
<span data-ttu-id="4ab82-120">\ket {1} _1 & \text{IF $ \ psi_1 $ är upptagen.}</span><span class="sxs-lookup"><span data-stu-id="4ab82-120">\ket{1}_1 & \text{if $\psi_1$ is occupied.}</span></span> <span data-ttu-id="4ab82-121">\end{Cases} \end{Equation} den här kodningen är perfekt för Quantum Computers eftersom det innebär att vi kan lagra den elektroniska yrket som en enda Quantum-bit.</span><span class="sxs-lookup"><span data-stu-id="4ab82-121">\end{cases} \end{equation} This encoding is great for quantum computers because it means that we can store the electronic occupation as a single quantum bit.</span></span>

<span data-ttu-id="4ab82-122">Yrkes tillstånden för $2N $-rotations banorna kan liknas på samma sätt i $2N $ qubits.</span><span class="sxs-lookup"><span data-stu-id="4ab82-122">The occupation states for the $2N$ spin orbitals can similarly be stored in $2N$ qubits.</span></span>
<span data-ttu-id="4ab82-123">Exempel: om $N = $2 sedan tillstånd $ $ \ket {0} \ket {1} \ket {1} \ket {0} , $ $</span><span class="sxs-lookup"><span data-stu-id="4ab82-123">As an example, if $N=2$ then the state $$ \ket{0} \ket{1} \ket{1} \ket{0}, $$</span></span>

<span data-ttu-id="4ab82-124">motsvarar rotations banaarna $1 $ och $2 $ som är upptagna med resten tom.</span><span class="sxs-lookup"><span data-stu-id="4ab82-124">would correspond to spin orbitals $1$ and $2$ being occupied with the remainder empty.</span></span>
<span data-ttu-id="4ab82-125">På samma sätt är tillstånd $ $ \ket {0} \equiv \ket {0} _ {0} \cdots \ket {0} _{N-1}, $ $</span><span class="sxs-lookup"><span data-stu-id="4ab82-125">Similarly, the state $$ \ket{0} \equiv \ket{0}_{0} \cdots \ket{0}_{N-1}, $$</span></span>

<span data-ttu-id="4ab82-126">har ingen electrons och kallas vakuum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="4ab82-126">has no electrons and is known as the 'vacuum state'.</span></span>

<span data-ttu-id="4ab82-127">En snygg sido effekt av andra kvantifieringsfel är att vi inte längre behöver hålla koll på antisymmetrin i Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="4ab82-127">A beautiful side-effect of second quantization is that we no longer have to explicitly keep track of the anti-symmetry of the quantum state.</span></span>
<span data-ttu-id="4ab82-128">Detta beror på att, som vi kommer att se, är antisymmetrin av statusen i stället i stället för de ansvariga operatörernas regler för att skapa och förstöra elektroniska yrken i ett varv orbital.</span><span class="sxs-lookup"><span data-stu-id="4ab82-128">This is because, as we will see, the anti-symmetry of the state represents itself instead through the anti-commutation rules of the operators that create and destroy electronic occupations of a spin orbital.</span></span>

## <a name="fermionic-operators"></a><span data-ttu-id="4ab82-129">Fermionic-operatörer</span><span class="sxs-lookup"><span data-stu-id="4ab82-129">Fermionic operators</span></span>

<span data-ttu-id="4ab82-130">De två grundläggande operatörerna som fungerar på de andra quantized-bas vektorerna kallas skapande-och Annihilation-operatörer.</span><span class="sxs-lookup"><span data-stu-id="4ab82-130">The two fundamental operators that act on the second-quantized basis vectors are known as creation and annihilation operators.</span></span>
<span data-ttu-id="4ab82-131">Dessa operatörer infogar eller förstör electrons på en viss plats.</span><span class="sxs-lookup"><span data-stu-id="4ab82-131">These operators insert or destroy electrons at a particular location.</span></span>
<span data-ttu-id="4ab82-132">Dessa betecknas $a ^ \ dagger_j $ och $a _j $ respektive.</span><span class="sxs-lookup"><span data-stu-id="4ab82-132">These are denoted $a^\dagger_j$ and $a_j$ respectively.</span></span>

<span data-ttu-id="4ab82-133">Till exempel \begin{align} a ^ \ dagger_1 \ket {0} _1 = \ket {1} _1, \quad a ^ \ dagger_1 \ket {1} _1 = 0, \quad A_1 \ket {0} _1 = 0, \quad A_1 \ket {1} _1 = \ket {0} _1.</span><span class="sxs-lookup"><span data-stu-id="4ab82-133">For example, \begin{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,\quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span></span>
<span data-ttu-id="4ab82-134">\end{align} Obs! här $a ^ \ dagger_1 \ket {1} _1 = 0 $ och $a _1 \ket {0} _1 $ ger noll-Vector inte $ \ket {0} _1 $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-134">\end{align} Note that here $a^\dagger_1 \ket{1}_1=0$ and $a_1 \ket{0}_1$ yield the zero-vector not $\ket{0}_1$.</span></span>
<span data-ttu-id="4ab82-135">Sådana operatörer är därför varken Hermitiana eller på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="4ab82-135">Such operators are therefore neither Hermitian nor unitary.</span></span>
<span data-ttu-id="4ab82-136">Vi representerar allmänna skapande-och Annihilation-operatörer med hjälp av <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> typen.</span><span class="sxs-lookup"><span data-stu-id="4ab82-136">We represent general creation and annihilation operators using the <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span></span>
<span data-ttu-id="4ab82-137">En enda skapande operator visas till exempel som följer.</span><span class="sxs-lookup"><span data-stu-id="4ab82-137">For instance, a single creation operator is represented as follow.</span></span>

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

<span data-ttu-id="4ab82-138">Även med sådana operatörer kan vi uttrycka $ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} ^ {\otimes 4}.</span><span class="sxs-lookup"><span data-stu-id="4ab82-138">Also using such operators we can express $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}^{\otimes 4}.</span></span>
<span data-ttu-id="4ab82-139">$ $ Den här sekvensen av operatörer skulle konstrueras i biblioteket för Hamiltonian-simulering med C#-kod som liknar orbital med ett enda varv som anses ovan:</span><span class="sxs-lookup"><span data-stu-id="4ab82-139">$$ This sequence of operators would be constructed within the Hamiltonian simulation library using C# code that is similar to the single-spin orbital case considered above above:</span></span>
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

<span data-ttu-id="4ab82-140">För ett system med $k $ Fermions, i andra kvantifieringsfel, har åtgärden att skapa operatör $a ^ \ dagger_i $ angetts av $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $ $ och $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, $ $ där $S _i = \ sum_ {j<i} a ^ \ dagger_j a_j $ mäter det totala antalet Fermions som är i samma tillstånd som en enskild partikel och som har ett index $j < i $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-140">For a system of $k$ Fermions, in second quantization the action of the creation operator $a^\dagger_i$ is given by $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $$ and $$ a^\dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k } = 0, $$ where $S_i = \sum_{j<i} a^\dagger_j a_j$ measures the total number of Fermions that are in the state of a single particle and that have an index $j < i$.</span></span>

<span data-ttu-id="4ab82-141">En tredje operator används också ofta i andra quantized-representationer.</span><span class="sxs-lookup"><span data-stu-id="4ab82-141">A third operator is also often used in second quantized representations.</span></span>
<span data-ttu-id="4ab82-142">Den här operatorn kallas för nummer operatorn och definieras av \begin{Equation} n_i = a ^ \ dagger_i a_i.</span><span class="sxs-lookup"><span data-stu-id="4ab82-142">This operator is known as the number operator and is defined by \begin{equation} n_i = a^\dagger_i a_i.</span></span>
<span data-ttu-id="4ab82-143">\end{Equation} den här operatorn räknar om en specifik orbital, vilket är att säga \begin{align} n_i \ket {0} _i &= 0 \ nonumber</span><span class="sxs-lookup"><span data-stu-id="4ab82-143">\end{equation} This operator counts the occupation of a given spin orbital, which is to say \begin{align} n_i \ket{0}_i &= 0\nonumber</span></span>\\\
<span data-ttu-id="4ab82-144">n_i \ket {1} _i &= \ket {1} _i.</span><span class="sxs-lookup"><span data-stu-id="4ab82-144">n_i \ket{1}_i &= \ket{1}_i.</span></span>
<span data-ttu-id="4ab82-145">\end{align} som liknar ovanstående `FermionTerm` exempel skapas den här nummer operatorn enligt följande.</span><span class="sxs-lookup"><span data-stu-id="4ab82-145">\end{align} Similar to the above `FermionTerm` examples, this number operator is constructed as follows.</span></span>
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

<span data-ttu-id="4ab82-146">En subtlety uppstår även när du använder skapande-eller Annihilation-operatörer i fermionic-system.</span><span class="sxs-lookup"><span data-stu-id="4ab82-146">A subtlety emerges though when using creation or annihilation operators in fermionic systems.</span></span>
<span data-ttu-id="4ab82-147">Vi kräver att alla giltiga Quantum-tillstånd är antisymmetriska i utbyte av etiketter.</span><span class="sxs-lookup"><span data-stu-id="4ab82-147">We require that any valid quantum state is anti-symmetric under exchange of labels.</span></span>
<span data-ttu-id="4ab82-148">Det innebär att $ $ a ^ \ dagger_2 a ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} .</span><span class="sxs-lookup"><span data-stu-id="4ab82-148">This means that $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span></span>
<span data-ttu-id="4ab82-149">$ $ Sådana operatörer säger att "anti-arbets" och allmänt för alla $i, j $ har \begin{align} a ^ \ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) a ^ \ dagger_j a ^ \ dagger_i, \quad a ^ \ dagger_i a_j = \ delta_ {i, j} – a_j a ^ \ dagger_i.</span><span class="sxs-lookup"><span data-stu-id="4ab82-149">$$ Such operators are said to 'anti-commute' and in general for any $i, j$ we have that \begin{align} a^\dagger_i a^\dagger_j  = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,\quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span></span>
<span data-ttu-id="4ab82-150">\end{align} därför betraktas följande två <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instanser som likvärdiga</span><span class="sxs-lookup"><span data-stu-id="4ab82-150">\end{align} Thus the following two <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances are considered inequivalent</span></span>
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

<span data-ttu-id="4ab82-151">Kravet på att var och en av de skapande operatörerna använder en andra quantized-representation gör så utmaningar med Fermions.</span><span class="sxs-lookup"><span data-stu-id="4ab82-151">The requirement that each of the creation operators anti-commute means that using a second quantized representation does obviate the challenges faced by the anti-symmetry of Fermions.</span></span>
<span data-ttu-id="4ab82-152">I stället visas utmaningen på nytt i vår definition av de skapande operatörerna.</span><span class="sxs-lookup"><span data-stu-id="4ab82-152">Instead the challenge re-emerges in our definition of the creation operators.</span></span> 

<span data-ttu-id="4ab82-153">Med hjälp av regler för att koppla från regler `LadderSequence` motsvarar vissa instanser faktiskt samma sekvens av fermionic-operatörer, ibland upp till ett minus tecken.</span><span class="sxs-lookup"><span data-stu-id="4ab82-153">Using the anti-commutation rules, some `LadderSequence` instances actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="4ab82-154">Anta till exempel att Hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-154">For instance, consider the Hamiltonian $a_0^\dagger a_1^\dagger a_1 a_0 = - a_1^\dagger a_0^\dagger a_1 a_0$.</span></span>
<span data-ttu-id="4ab82-155">Detta motiverar oss att definiera en kanonisk ordning för var och en `FermionTerm` .</span><span class="sxs-lookup"><span data-stu-id="4ab82-155">This motivates us to define a canonical ordering for every `FermionTerm`.</span></span>
<span data-ttu-id="4ab82-156">Alla sätts `FermionTerm` automatiskt in i den kanoniska ordningen enligt följande.</span><span class="sxs-lookup"><span data-stu-id="4ab82-156">Any `FermionTerm` is automatically put into canonical order as follows.</span></span>
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a><span data-ttu-id="4ab82-157">Andra – quantized Fermionic-Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="4ab82-157">Second-Quantized Fermionic Hamiltonian</span></span>

<span data-ttu-id="4ab82-158">Det är kanske unsurprising att Hamiltonian i [Quantum-modeller för elektroniska system](xref:microsoft.quantum.chemistry.concepts.quantummodels) kan skrivas i form av skapande-och Annihilation-operatörer.</span><span class="sxs-lookup"><span data-stu-id="4ab82-158">It is perhaps unsurprising that the Hamiltonian in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) can be written in terms of creation and annihilation operators.</span></span>
<span data-ttu-id="4ab82-159">I synnerhet, om $ \psi \_ j $ är de rotations banor som utgör grunden</span><span class="sxs-lookup"><span data-stu-id="4ab82-159">In particular, if $\psi\_j$ are the spin orbitals that form the basis then</span></span>

<span data-ttu-id="4ab82-160">\begin{Equation} \hat{H} = \sum \_ {PQ} H \_ {PQ} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {PQRS} H \_ {PQRS} a ^ \dagger \_ p a ^ \dagger \_ q a \_ ra \_ s + h \_ {\textrm NUC}, \label{EQ: totalHam} \end{Equation} där $h \_ {\Textrm NUC} $ är kärn energin (som är konstant under den födda-Oppenheimer-uppskattningen) och</span><span class="sxs-lookup"><span data-stu-id="4ab82-160">\begin{equation} \hat{H} = \sum\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} where $h\_{\textrm nuc}$ is the nuclear energy (which is a constant under the Born-Oppenheimer approximation) and</span></span>

<span data-ttu-id="4ab82-161">\begin{align} h \_ {PQ} &= \int \_ {-\infty} ^ \infty \psi ^ \* \_ p (x \_ 1) \left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \psi \_ q (x \_ 1) \mathrm{d} ^ 3x \_ 1, \end{align}</span><span class="sxs-lookup"><span data-stu-id="4ab82-161">\begin{align} h\_{pq} &= \int\_{-\infty}^\infty \psi^\*\_p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\right)  \psi\_q(x\_1)\mathrm{d}^3x\_1, \end{align}</span></span>

<span data-ttu-id="4ab82-162">där $V (x) $ är potentialen medel fält och</span><span class="sxs-lookup"><span data-stu-id="4ab82-162">where $V(x)$ is the mean-field potential, and</span></span>

<span data-ttu-id="4ab82-163">\begin{align} h \_ {PQRS} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \psi \_ q ^ \* (x \_ 2) \left (\frac {1} {| x_1-x_2 |} \right) \psi \_ r (x \_ 2) \psi \_ s (x \_ 1) \mathrm{d} ^ 3x \_ 1 \ mathrm {d} ^ 3x \_ 2. \ Label {EQ: integraler} \end{align}</span><span class="sxs-lookup"><span data-stu-id="4ab82-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\infty \int\_{-\infty}^\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{|x_1-x_2|} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq:integrals} \end{align}</span></span>

<span data-ttu-id="4ab82-164">Termerna $h \_ {PQ} $ kallas en-Electron integraler eftersom alla sådana termer bara omfattar enskilda electrons och även $h \_ {PQRS} $ är de två Electron integralerna.</span><span class="sxs-lookup"><span data-stu-id="4ab82-164">The terms $h\_{pq}$ are referred to as one-electron integrals because all such terms only involve single electrons and likewise $h\_{pqrs}$ are the two-electron integrals.</span></span>
<span data-ttu-id="4ab82-165">De kallas integraler eftersom beräkning av värdena för dessa koefficienter kräver en integral.</span><span class="sxs-lookup"><span data-stu-id="4ab82-165">They are called integrals because computing the values of these coefficients requires an integral.</span></span>
<span data-ttu-id="4ab82-166">Det enda villkoret för Electron beskriver den enskilda electrons och deras interaktioner med de elektriska fälten i kärnor.</span><span class="sxs-lookup"><span data-stu-id="4ab82-166">The one electron terms describe the kinetic energy of the individual electrons and their interactions with the electric fields of the nuclei.</span></span>
<span data-ttu-id="4ab82-167">De två Electron-integralerna å andra sidan beskriver interaktionerna mellan electrons.</span><span class="sxs-lookup"><span data-stu-id="4ab82-167">The two-electron integrals on the other hand describe the interactions between the electrons.</span></span>

<span data-ttu-id="4ab82-168">En intuition för det här villkoret kan vara uppnår från skapande-och Annihilation-operatörerna som omfattar var och en av dem.</span><span class="sxs-lookup"><span data-stu-id="4ab82-168">An intuition for what these terms mean can be gleaned from the creation and annihilation operators that comprise each of them.</span></span>
<span data-ttu-id="4ab82-169">Exempel: $h _ {PQ} a ^ \ dagger_p a_q $ beskriver Electron hoppande från rotation orbital $q $ för att snurra orbital $p $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-169">For example, $h_{pq}a^\dagger_p a_q$ describes the electron hopping from spin orbital $q$ to spin orbital $p$.</span></span>
<span data-ttu-id="4ab82-170">På samma sätt beskriver termen $h _ {PQRS} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (för distinkta $p, q, r, s $) två electrons i rotations banaarna $r $ och $s $-spridning av varandra och du avslutar i rotations banorna $p $ och $q $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-170">Similarly, the term $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (for distinct $p,q,r,s$) describes two electrons in spin orbitals $r$ and $s$ scattering off of each other and ending up in spin orbitals $p$ and $q$.</span></span>
<span data-ttu-id="4ab82-171">Om $r = q $ och $p = s $ sedan $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ ger den energi påföljd som är kopplad till de två electrons nära varandra, men beskriver inte en dynamisk process.</span><span class="sxs-lookup"><span data-stu-id="4ab82-171">If $r=q$ and $p=s$ then $h_{prrp} a^\dagger_p a^\dagger_r a_r a_p = h_{prrp} n_p n_r$ gives the energy penalty associated with the two electrons being near each other, but does not describe a dynamical process.</span></span>

<span data-ttu-id="4ab82-172">Vi kan representera sådana Hamiltonians med hjälp av `FermionHamiltonian` klassen, som är i grunden en lista som innehåller alla önskade `FermionTerm` instanser.</span><span class="sxs-lookup"><span data-stu-id="4ab82-172">We may represent such Hamiltonians using the `FermionHamiltonian` class, which is essentially a list containing all the desired `FermionTerm` instances.</span></span>
<span data-ttu-id="4ab82-173">Eftersom Hamiltonians är Hermitian definitions mässigt indexerar vi termerna med hjälp av en mer specialiserad typ `HermitianFermionTerm` som också använder Hermitian-symmetri när de kontrollerar om villkoren är likvärdiga.</span><span class="sxs-lookup"><span data-stu-id="4ab82-173">As Hamiltonians are Hermitian by definition, we index terms using the more specialized type `HermitianFermionTerm` that also uses Hermitian symmetry when checking whether terms are equivalent.</span></span>

<span data-ttu-id="4ab82-174">Låt oss skapa några exempel på exempel.</span><span class="sxs-lookup"><span data-stu-id="4ab82-174">Let us construct a few illustrative examples.</span></span>
<span data-ttu-id="4ab82-175">Överväg Hamiltonian $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-175">Consider the Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
<span data-ttu-id="4ab82-176">Vi kan förenkla denna konstruktion med det faktum att Hamiltonian-operatörer är Hermitian-operatörer.</span><span class="sxs-lookup"><span data-stu-id="4ab82-176">We may simplify this construction using the fact that Hamiltonian operators are Hermitian operators.</span></span>
<span data-ttu-id="4ab82-177">När du lägger till villkor i Hamiltonian med `Add` , antas alla icke-Hermitian, till exempel, `fermionTerm0` kombineras med dess Hermitian-konjugat.</span><span class="sxs-lookup"><span data-stu-id="4ab82-177">When adding terms to the Hamiltonian using `Add`, any non-Hermitian term such as `fermionTerm0` is assumed to be paired with its Hermitian conjugate.</span></span>
<span data-ttu-id="4ab82-178">Följande kodfragment representerar därför också samma Hamiltonian:</span><span class="sxs-lookup"><span data-stu-id="4ab82-178">Thus the following snippet also represents the same Hamiltonian:</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

<span data-ttu-id="4ab82-179">Med hjälp av regler för att koppla från regler, `FermionTerm` motsvarar vissa instanser i Hamiltonian samma sekvens med fermionic-operatörer, ibland upp till ett minus tecken.</span><span class="sxs-lookup"><span data-stu-id="4ab82-179">Using the anti-commutation rules, some `FermionTerm` instances in the Hamiltonian actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="4ab82-180">Anta till exempel att Hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $, som är en summa av de termer som skapats ovan.</span><span class="sxs-lookup"><span data-stu-id="4ab82-180">For instance, consider the Hamiltonian $H=a_0^\dagger a_1^\dagger a_1 a_0 - a_1^\dagger a_0^\dagger a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, which is a sum of terms constructed above.</span></span>
<span data-ttu-id="4ab82-181">Det är inte alltid uppenbart att användaren har motsvarande villkor, och därför kan de läggas till i Hamiltonian separat.</span><span class="sxs-lookup"><span data-stu-id="4ab82-181">It may not always be clear to the user that these are equivalent terms, and so they may be added to the Hamiltonian separately.</span></span>
<span data-ttu-id="4ab82-182">Det kan också vara intressant att ändra redan befintliga termer i Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="4ab82-182">Alternatively, one may be interested in modifying already-existing terms in the Hamiltonian.</span></span>
<span data-ttu-id="4ab82-183">I dessa fall kan vi kombinera motsvarande termer på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="4ab82-183">In these cases, we may combine equivalent terms as follows.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
<span data-ttu-id="4ab82-184">Genom att kombinera koefficienter med likvärdiga villkor minskar vi det totala antalet villkor i Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="4ab82-184">By combining coefficients of equivalent terms, we reduce the total number of terms in the Hamiltonian.</span></span>
<span data-ttu-id="4ab82-185">Senare, minskar detta antalet Quantum-grindar som krävs för att simulera Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="4ab82-185">Later on, this reduces the number of quantum gates required to simulate the Hamiltonian.</span></span>

### <a name="internal-representation"></a><span data-ttu-id="4ab82-186">Intern representation</span><span class="sxs-lookup"><span data-stu-id="4ab82-186">Internal Representation</span></span>

<span data-ttu-id="4ab82-187">En fermionic-Hamiltonian med en och två-Body-interaktioner visas i quantized-notation som</span><span class="sxs-lookup"><span data-stu-id="4ab82-187">A fermionic Hamiltonian with one- and two-body interactions is represented in second-quantized notation as</span></span>

<span data-ttu-id="4ab82-188">$ $ \begin{align} H = \sum \_ {PQ} H \_ {PQ} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {PQRS} H \_ {PQRS} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a { \_ r} a \_ {s}.</span><span class="sxs-lookup"><span data-stu-id="4ab82-188">$$ \begin{align} H=\sum\_{pq}h\_{pq}a^\dagger\_{p}a\_{q}+\frac{1}{2}\sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}.</span></span>
<span data-ttu-id="4ab82-189">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="4ab82-189">\end{align} $$</span></span>

<span data-ttu-id="4ab82-190">I det här formatet finns högst $N ^ 2 + N ^ 4 $ koefficienter.</span><span class="sxs-lookup"><span data-stu-id="4ab82-190">In this notation, there are at most $N^2+N^4$ coefficients.</span></span>
<span data-ttu-id="4ab82-191">Många av dessa koefficienter kan dock samlas in när de motsvarar samma operatör.</span><span class="sxs-lookup"><span data-stu-id="4ab82-191">However, many of these coefficients may be collected as they correspond to the same operator.</span></span>
<span data-ttu-id="4ab82-192">Till exempel, i fall där $p, q, r, s $ är distinkta index, vi kan använda regler för att se till att: $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger \_ {p} a { \_ r} a { \_ s} =-a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {s} a { \_ r} = a ^ \dagger \_ {q} a ^ \dagger \_ {p} a { \_ \_ r}.</span><span class="sxs-lookup"><span data-stu-id="4ab82-192">For instance, in the case where $p,q,r,s$ are distinct indices, we may use the anti-commutation rules to show that: $$ a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r}a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span></span>
$$

<span data-ttu-id="4ab82-193">Dessutom är $H $ Hermitian, varje icke-Hermitian fermionic-Operator, säg $h \_ {PQRS} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a {r} a {s} \_ \_ $, har ett Hermitian-konjugat som också finns i $H $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-193">Furthermore, as $H$ is Hermitian, every non-Hermitian fermionic operator, say $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, has a Hermitian conjugate that is also found in $H$.</span></span> <span data-ttu-id="4ab82-194">För att unikt indexera grupper av termer som karakteriseras av dessa symmetries, vi definierar en kanonisk ordning på indexen $ (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) $ i en sekvens med $n + m $ fermionic-operatörer $a ^ \dagger \_ {i \_ 1} \cdots a ^ \dagger \_ {i \_ n} a \_ {j \_ 1} \cdots a \_ {j \_ m} $as följande:</span><span class="sxs-lookup"><span data-stu-id="4ab82-194">In order to uniquely index groups of terms characterized by these symmetries, we define a canonical ordering on the indices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ of any sequence of $n+m$ fermionic operators $a^\dagger\_{i\_1}\cdots a^\dagger\_{i\_n}a\_{j\_1}\cdots a\_{j\_m}$as follows:</span></span>
-   <span data-ttu-id="4ab82-195">Alla operatorer för skapande $a ^ \dagger \_ {i \_ \cdot} $ placeras före alla Annihilation-operatörer $a \_ {j \_ \cdot} $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-195">All creation operators $a^\dagger\_{i\_\cdot}$ are placed before all annihilation operators $a\_{j\_\cdot}$.</span></span>
-   <span data-ttu-id="4ab82-196">Alla index för skapande operatorer sorteras i stigande ordning, vilket är $i \_ 1< i \_ 2< \cdots < i \_ n $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-196">All creation operator indices are sorted in ascending order, that is $i\_1< i\_2< \cdots < i\_n$.</span></span>
-   <span data-ttu-id="4ab82-197">Alla index för Annihilation-operatorer sorteras i fallande ordning, det vill säga $j \_ 1> j \_ 2 \cdots > j \_ m $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-197">All annihilation operator indices are sorted in descending order, that is $j\_1> j\_2 \cdots > j\_m$.</span></span>
-   <span data-ttu-id="4ab82-198">Det vänstra indexet är mindre än eller lika med det högra indexet, det vill säga $i \_ 1 \ Le j \_ m $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-198">The left-most index is less than or equal to the right-most index, that is $i\_1\le j\_m$.</span></span>

<span data-ttu-id="4ab82-199">Låt oss identifiera den här uppsättningen av kanoniskt sorterade index som $ $ \begin{align} (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) \in S \_ {n, m}.</span><span class="sxs-lookup"><span data-stu-id="4ab82-199">Let us identify this set of canonically ordered indices as $$ \begin{align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span></span>
<span data-ttu-id="4ab82-200">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="4ab82-200">\end{align} $$</span></span>

<span data-ttu-id="4ab82-201">Med den här kanoniska ordningen kan fermionic-Hamiltonian uttryckas som $ $ \begin{align} H = \sum \_ {(p, q) \In S \_ {1,1} } H ' \_ {PQ} \frac{a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger \_ {q} a \_ {p}} {2} + \sum \_ {(p, q, r, s) \in s \_ {2,2} } H \_ {PQRS} \frac{a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {S} + a ^ \dagger \_ {S} a ^ \dagger \_ {r} a \_ {q} a \_ {p}} {2} , \end{align} $ $ med lämpligt anpassat en-och två Electron-integraler $h \_ {PQ} $ och $h \_ {PQRS} $.</span><span class="sxs-lookup"><span data-stu-id="4ab82-201">With this canonical ordering, the fermionic Hamiltonian may be expressed as $$ \begin{align} H=\sum\_{(p,q)\in S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\dagger\_{q}a\_{p}}{2}+\sum\_{(p,q,r,s)\in S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\dagger\_{s}a^\dagger\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ with suitably adapted one- and two-electron integrals $h'\_{pq}$ and $h'\_{pqrs}$, respectively.</span></span>

