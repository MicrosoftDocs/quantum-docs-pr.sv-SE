---
title: Simulera Hamiltonian Dynamics
description: Lär dig hur du använder Trotter-Suzuki formler och qubitization för att arbeta med Hamiltonian-simuleringar.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 5dad4e4a77eea99e72eb2efac52eec61ebbdb21c
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320715"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="a0241-103">Simulera Hamiltonian Dynamics</span><span class="sxs-lookup"><span data-stu-id="a0241-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="a0241-104">När Hamiltonian har utsetts som en summa av element operatörer kan Dynamics kompileras till grundläggande grind åtgärder med hjälp av en värd med välkända tekniker.</span><span class="sxs-lookup"><span data-stu-id="a0241-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="a0241-105">Det finns tre effektiva metoder som är Trotter – Suzuki formler, linjära kombinationer av unitaries och qubitization.</span><span class="sxs-lookup"><span data-stu-id="a0241-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="a0241-106">Vi förklarar dessa tre metoder och ger konkreta Q #-exempel på hur du implementerar dessa metoder med Hamiltonian Simulator Library.</span><span class="sxs-lookup"><span data-stu-id="a0241-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="a0241-107">Trotter – Suzuki formler</span><span class="sxs-lookup"><span data-stu-id="a0241-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="a0241-108">Idén bakom Trotter – Suzuki formler är enkla: uttrycka Hamiltonian som en summa av enkel för att simulera Hamiltonians och sedan uppskatta den totala utvecklingen som en följd av dessa enklare utvecklingar.</span><span class="sxs-lookup"><span data-stu-id="a0241-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="a0241-109">I synnerhet ska $H = \ sum_ {j = 1} ^ m H_j $ vara Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="a0241-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="a0241-110">Sedan $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, vilket innebär att om $t \ll $1, blir felet i den här uppskattningen försumbar.</span><span class="sxs-lookup"><span data-stu-id="a0241-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="a0241-111">Observera att om $e ^ {-i H t} $ var en vanlig exponent, skulle felet i den här uppskattningen inte vara $O (m ^ 2 t ^ 2) $: det skulle vara noll.</span><span class="sxs-lookup"><span data-stu-id="a0241-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="a0241-112">Det här felet beror på att $e ^ {-iHt} $ är en operator exponentiell och därför att det uppstår ett fel när du använder den här formeln på grund av att $H _j $-villkoren inte går ut (*d.v.s.* $H _J H_k \ne H_k $ i allmänhet).</span><span class="sxs-lookup"><span data-stu-id="a0241-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute (*i.e.*, $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="a0241-113">Om $t $ är stor kan Trotter – Suzuki-formler fortfarande användas för att simulera Dynamicset korrekt genom att dela upp det i en sekvens med korta tids steg.</span><span class="sxs-lookup"><span data-stu-id="a0241-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="a0241-114">Låt $r $ vara det antal steg som har vidtagits under tids utvecklingen, så varje gång steg körs för tid $t/r $.</span><span class="sxs-lookup"><span data-stu-id="a0241-114">Let $r$ be the number of steps taken in the time evolution, so each time step runs for time $t/r$.</span></span> <span data-ttu-id="a0241-115">Sedan har vi den $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ höger) ^ r + O (m ^ 2 t ^ 2/r). $ $ som innebär att om $r $ skalas som $m ^ 2 t ^ 2/\ Epsilon $ kan felet göras högst $ \epsilon $ för alla $ \epsilon > 0 $.</span><span class="sxs-lookup"><span data-stu-id="a0241-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="a0241-116">Mer exakta uppskattningar kan byggas genom att skapa en sekvens med operatorer exponentiella så att fel villkoren avbryts.</span><span class="sxs-lookup"><span data-stu-id="a0241-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="a0241-117">Den enklaste formeln, den andra ordningen Trotter-Suzuki formel, tar formuläret $ $ U_2 (t) = \left (\ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2R} \ prod_ {j = m} ^ 1 e ^ {-iH_j t/2R} \ Right) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2), $ $ ett fel som kan göras mindre än $ \epsilon $ för alla $ \epsilon > 0 $ genom att välja $r $ för att skala som $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $.</span><span class="sxs-lookup"><span data-stu-id="a0241-117">The simplest such formula, the second order Trotter-Suzuki formula, takes the form $$ U_2(t) = \left(\prod_{j=1}^{m} e^{-iH_j t/2r} \prod_{j=m}^1 e^{-iH_j t/2r}\right)^r = e^{-iHt} + O(m^3 t^3/r^2), $$ the error of which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="a0241-118">Även formler med högre ordning, särskilt ($ 2 $) för $k > 0 $, kan konstrueras rekursivt: $ $ U_ {2 000} (t) = [U_  (s_k\~ t)] ^ 2 U_  ([1-4s_k] t) [U_ {2-2} (s_k\~ t)] ^ 2 = e ^ {-iHt} + O ((m t) ^ {2 000 + 1}/r ^ ), $ $ WHERE $s _k = (4-4 ^ {1/(2 000-1)}) ^{-1}$.</span><span class="sxs-lookup"><span data-stu-id="a0241-118">Even higher-order formulas, specifically ($2k$)th-order for $k>0$, can be constructed recursively: $$ U_{2k}(t) = [U_{2k-2}(s_k\~ t)]^2 U_{2k-2}([1-4s_k]t) [U_{2k-2}(s_k\~ t)]^2 = e^{-iHt} + O((m t)^{2k+1}/r^{2k}), $$ where $s_k = (4-4^{1/(2k-1)})^{-1}$.</span></span>

<span data-ttu-id="a0241-119">Det enklaste är följande fjärde order ($k = $2) formel, som ursprungligen introducerades av Suzuki: $ $ U_4 (t) = [U_2 (s_2\~ t)] ^ 2 U_2 ([1-4s_2] t) [U_2 (s_2\~ t)] ^ 2 = e ^ {-iHt} + O (m ^ 5T ^ 5). $ $ Where $s _2 = (4-4 ^ {1/3}) ^{-1}$.</span><span class="sxs-lookup"><span data-stu-id="a0241-119">The simplest is the following fourth order ($k=2$) formula, originally introduced by Suzuki: $$ U_4(t) = [U_2(s_2\~ t)]^2 U_2([1-4s_2]t) [U_2(s_2\~ t)]^2 = e^{-iHt} +O(m^5t^5/r^4), $$ where $s_2 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="a0241-120">I allmänhet kan godtyckliga formler med hög ordning skapas på samma sätt; kostnaderna för att använda mer komplexa integrerare uppväger dock ofta fördelarna bortom den fjärde ordningen för de flesta praktiska problemen.</span><span class="sxs-lookup"><span data-stu-id="a0241-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="a0241-121">För att se till att strategierna ovan fungerar måste vi ha en metod för att simulera en bred klass $e ^ {-iH_j t} $.</span><span class="sxs-lookup"><span data-stu-id="a0241-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="a0241-122">Den enklaste familjen av Hamiltonians och utan tvekan mest användbar, som vi kan använda här är Pauli-operatörer.</span><span class="sxs-lookup"><span data-stu-id="a0241-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="a0241-123">Pauli-operatörer kan enkelt simuleras eftersom de kan diagonalt med Clifford-åtgärder (som är standard grindar i Quantum Computing).</span><span class="sxs-lookup"><span data-stu-id="a0241-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="a0241-124">Efter att de har blivit diagonala kan deras Eigenvalues hittas genom att pariteten för de qubits som fungerar.</span><span class="sxs-lookup"><span data-stu-id="a0241-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="a0241-125">Till exempel $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ WHERE $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="a0241-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="a0241-126">0 & e ^ {i t} & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="a0241-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="a0241-127">0 & 0 & e ^ {IT} & 0 </span><span class="sxs-lookup"><span data-stu-id="a0241-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="a0241-128">0 & 0 & 0 & e ^ {-IT} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="a0241-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="a0241-129">$ $ Här, $e ^ {-iHt} \ket{00} = e ^ {IT} \ket{00}$ och $e ^ {-iHt} \ket{01} = e ^ {-IT} \ket{01}$, som kan visas direkt till följd av det faktum att pariteten för $0 $ är $0 $ medan pariteten för bit strängen $1 $ är $1 $.</span><span class="sxs-lookup"><span data-stu-id="a0241-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="a0241-130">Exponenter för Pauli-operatörer kan implementeras direkt i Q # med <xref:microsoft.quantum.intrinsic.exp>-åtgärden:</span><span class="sxs-lookup"><span data-stu-id="a0241-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:microsoft.quantum.intrinsic.exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="a0241-131">För Fermionic Hamiltonians mappar den [Jordanien-Wigner diskompositionen](xref:microsoft.quantum.chemistry.concepts.jordanwigner) enkelt in Hamiltonian i en summa av Pauli-operatörer.</span><span class="sxs-lookup"><span data-stu-id="a0241-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="a0241-132">Det innebär att ovanstående metod enkelt kan anpassas till att simulera kemi.</span><span class="sxs-lookup"><span data-stu-id="a0241-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="a0241-133">I stället för att manuellt loopa över alla Pauli-termer i Wigner-representationen nedan är ett enkelt exempel på hur en sådan simulering i kemi skulle se ut.</span><span class="sxs-lookup"><span data-stu-id="a0241-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how executing such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="a0241-134">Vår start punkt är en [Jordanien – Wigner kodning](xref:microsoft.quantum.chemistry.concepts.jordanwigner) av Fermionic-Hamiltonian, uttryckt i kod som en instans av klassen `JordanWignerEncoding`.</span><span class="sxs-lookup"><span data-stu-id="a0241-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

<span data-ttu-id="a0241-135">Det här formatet på den Jordanien – Wigner-representation som används av algoritmerna för Q #-simulering är en användardefinierad typ `JordanWignerEncodingData`.</span><span class="sxs-lookup"><span data-stu-id="a0241-135">This format of the Jordan–Wigner representation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="a0241-136">I Q # skickas det här formatet till en bekvämlighets funktion `TrotterStepOracle` som returnerar en operator som uppskattar tids utvecklingen med hjälp av Trotter – Suzuki Integrator, förutom andra parametrar som krävs för att köra den.</span><span class="sxs-lookup"><span data-stu-id="a0241-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its execution.</span></span>

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

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="a0241-137">För den här implementeringen används till exempel vissa optimeringar som diskuteras i [simuleringen av elektronisk struktur Hamiltonians med Quantum Computers](https://arxiv.org/abs/1001.3855) och [förbättrar Quantum-algoritmer för Quantum kemi](https://arxiv.org/abs/1403.1539) för att minimera antalet enskilda qubit-rotationer, samt minska simulerings fel.</span><span class="sxs-lookup"><span data-stu-id="a0241-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="a0241-138">Qubitization</span><span class="sxs-lookup"><span data-stu-id="a0241-138">Qubitization</span></span>

<span data-ttu-id="a0241-139">Qubitization är en alternativ metod för simulering som använder idéer från Quantum-instruktioner för att simulera Quantum Dynamics.</span><span class="sxs-lookup"><span data-stu-id="a0241-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="a0241-140">Medan qubitization kräver fler qubits än Trotter-formler, lovar metoden optimal skalning med utvecklings tiden och fel toleransen.</span><span class="sxs-lookup"><span data-stu-id="a0241-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="a0241-141">Därför har det blivit en prioriterad metod för att simulera Hamiltonian Dynamics i allmänhet och för att lösa det elektroniska struktur problemet i synnerhet.</span><span class="sxs-lookup"><span data-stu-id="a0241-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="a0241-142">På hög nivå uppnår qubitization detta genom följande steg.</span><span class="sxs-lookup"><span data-stu-id="a0241-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="a0241-143">Börja med att låta $H = \ sum_j h_j H_j $ för välHermitiane och $H _j $ och $h _j \ge $0.</span><span class="sxs-lookup"><span data-stu-id="a0241-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="a0241-144">Genom att utföra ett par av reflektioner implementerar qubitization en operator som motsvarar $ $W = e ^ {\pm i \cos ^{-1}(H/| h | _1)}, $ $ där $ | H | _1 = \ sum_j | h_j | $.</span><span class="sxs-lookup"><span data-stu-id="a0241-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="a0241-145">Nästa steg är att transformera Eigenvalues av en LED-operator från $e ^ {i\pm \cos ^{-1}(E_k/| h | _1)} $, där $E _k $ är Eigenvalues $H $ till $e ^ {-iE_k t} $.</span><span class="sxs-lookup"><span data-stu-id="a0241-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="a0241-146">Detta kan uppnås med hjälp av en mängd olika metoder för att omvandla Quantum-värden, inklusive [bearbetning av Quantum-signaler](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span><span class="sxs-lookup"><span data-stu-id="a0241-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="a0241-147">Alternativt, om bara statiska kvantiteter är önskade (t. ex. Hamiltonian), så räcker det att tillämpa [fas uppskattningen](xref:microsoft.quantum.libraries.characterization) direkt på $W $ för att beräkna mark tillståndets energi från resultatet genom att ta cosinus av resultatet.</span><span class="sxs-lookup"><span data-stu-id="a0241-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="a0241-148">Detta är viktigt eftersom det gör att Spectral-transformeringen kan utföras klassiskt i stället för att använda en metod för att omvandla en Quantum-värde.</span><span class="sxs-lookup"><span data-stu-id="a0241-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="a0241-149">På en mer detaljerad nivå kräver implementeringen av qubitization två under rutiner som tillhandahåller gränssnitten för Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="a0241-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="a0241-150">Till skillnad från Trotter – Suzuki-metoder är dessa underrutinerna Quantum inte för klassisk användning och implementeringen kommer att kräva att logarithmically fler qubits än skulle krävas för en Trotter-baserad simulering.</span><span class="sxs-lookup"><span data-stu-id="a0241-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="a0241-151">Den första Quantum-underrutinen som qubitization använder kallas $ \operatorname{Select} $ och det är lovat att ge \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation} där varje $H _j $ antas vara Hermitian och enhetlighet.</span><span class="sxs-lookup"><span data-stu-id="a0241-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="a0241-152">Även om det kan förefalla vara restriktivt, kom ihåg att Pauli-operatörerna är Hermitian och på samma sätt och att program som Quantum kemi-simulering i naturlig utsträckning omfattas av detta ramverk.</span><span class="sxs-lookup"><span data-stu-id="a0241-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="a0241-153">$ \Operatorname{Select} $-åtgärden, kanske överraskande, är i själva verket en reflektions åtgärd.</span><span class="sxs-lookup"><span data-stu-id="a0241-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="a0241-154">Detta kan ses från det faktum att $ \operatorname{Select} ^ 2 \ ket {j} \ket{\psi} = \ket{j} \ket{\psi} $, eftersom varje $H _j $ är enhetlig och Hermitian och därför har Eigenvalues $ \pm $1.</span><span class="sxs-lookup"><span data-stu-id="a0241-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="a0241-155">Den andra subrutinen kallas $ \operatorname{Prepare} $.</span><span class="sxs-lookup"><span data-stu-id="a0241-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="a0241-156">Medan Select-åtgärden ger en konsekvent åtkomst till var och en av Hamiltonian termer $H _j $, ger en metod för att komma åt koefficienterna $h _j $, \begin{Equation} \operatorname{Prepare}\ket{0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="a0241-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="a0241-157">\end{Equation}, med hjälp av en multiplicering-kontrollerad fas grind, ser vi att $ $ \Lambda\ket{0}^ {\otimes n} = \begin{Cases} \-\ket{x} & \text{IF} x = 0 </span><span class="sxs-lookup"><span data-stu-id="a0241-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="a0241-158">\ket{x} & \text{otherwise} \end{cases}.</span><span class="sxs-lookup"><span data-stu-id="a0241-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="a0241-159">$ \Operatorname{Prepare} $-åtgärden används inte direkt i qubitization, utan används i stället för att implementera en reflektion om det tillstånd som $ \operatorname{Prepare} $ skapar $ $ \begin{align} R &amp; = 1-2 \ operatorname {prepare} \ket{0}\bra{0} \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}.</span><span class="sxs-lookup"><span data-stu-id="a0241-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="a0241-160">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a0241-160">\end{align} $$</span></span>

<span data-ttu-id="a0241-161">Operatorn guida, $W $, kan uttryckas som $ \operatorname{Select} $ och $R $-åtgärder som $ $ W = \operatorname{Select} R, $ $ som återigen kan ses för att implementera en operatör som är likvärdig (upp till en isometry) att $e ^ {\pm i \cos ^{-1}(H/| H | _1)} $.</span><span class="sxs-lookup"><span data-stu-id="a0241-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="a0241-162">Dessa under rutiner är enkla att konfigurera i Q #.</span><span class="sxs-lookup"><span data-stu-id="a0241-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="a0241-163">Som exempel bör du överväga den enkla qubit-Ising Hamiltonian där $H = X_1 + X_2 + Z_1 Z_2 $.</span><span class="sxs-lookup"><span data-stu-id="a0241-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="a0241-164">I det här fallet anropas den Q #-kod som implementerar $ \operatorname{Select} $-åtgärden av <xref:microsoft.quantum.canon.multiplexoperations>, medan $ \operatorname{Prepare} $-åtgärden kan implementeras med hjälp av <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span><span class="sxs-lookup"><span data-stu-id="a0241-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:microsoft.quantum.canon.multiplexoperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span></span>
<span data-ttu-id="a0241-165">Ett exempel som inbegriper simulering av Hubbard-modellen finns som ett [Q #-exempel](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).</span><span class="sxs-lookup"><span data-stu-id="a0241-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).</span></span>

<span data-ttu-id="a0241-166">Att manuellt ange dessa steg för valfria kemi-problem skulle kräva mycket ansträngning, vilket undviks med hjälp av kemi-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="a0241-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="a0241-167">På samma sätt som för Trotter – Suzuki simulerings algoritmen ovan skickas `JordanWignerEncodingData` till den bekvämlighets funktion `QubitizationOracle` som returnerar en funktions Operator, förutom andra parametrar som krävs för körningen.</span><span class="sxs-lookup"><span data-stu-id="a0241-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="a0241-168">Det är viktigt att implementerings <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> tillämpas på godtycklig Hamiltonians som anges som en linjär kombination av Pauli-strängar.</span><span class="sxs-lookup"><span data-stu-id="a0241-168">Importantly, the implementation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="a0241-169">En version som är optimerad för kemi-simuleringar anropas med hjälp av <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span><span class="sxs-lookup"><span data-stu-id="a0241-169">A version optimized for chemistry simulations is invoked using <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span></span>
<span data-ttu-id="a0241-170">Den här versionen är optimerad för att minimera antalet T-portar med hjälp av tekniker som beskrivs i [koda elektroniska Spectra i Quantum-kretsar med linjär T-komplexitet](https://arxiv.org/abs/1805.03662).</span><span class="sxs-lookup"><span data-stu-id="a0241-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
