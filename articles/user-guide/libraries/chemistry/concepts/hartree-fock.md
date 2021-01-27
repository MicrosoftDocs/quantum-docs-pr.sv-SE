---
title: Hartree-Fock teori
description: Lär dig mer om Hartree – Fock teori, ett enkelt sätt att skapa det ursprungliga läget för Quantum Systems.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.hartreefock
no-loc:
- Q#
- $$v
ms.openlocfilehash: 48d6bc4face90046271dd8705188a92daafad98a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854098"
---
# <a name="hartreefock-theory"></a><span data-ttu-id="70a36-103">Hartree – Fock teori</span><span class="sxs-lookup"><span data-stu-id="70a36-103">Hartree–Fock Theory</span></span>

<span data-ttu-id="70a36-104">Kanske är den viktigaste mängden i Quantum kemi-simuleringen jord, vilket är den minsta energi eigenvector i Hamiltonian-matrisen.</span><span class="sxs-lookup"><span data-stu-id="70a36-104">Perhaps the most important quantity in quantum chemistry simulation is the ground state, which is the minimum energy eigenvector of the Hamiltonian matrix.</span></span>
<span data-ttu-id="70a36-105">Detta beror på att för de flesta molekylerna vid rums temperatur, till exempel reaktions taxan, domineratss genom kostnads fria energi skillnader mellan Quantum-tillstånd som beskriver början och slutet av ett steg i en reaktions väg och vid rums temperatur är det vanligt vis jord tillstånd.</span><span class="sxs-lookup"><span data-stu-id="70a36-105">This is because for most molecules at room temperature quantities such as reaction rates are dominated by free energy differences between quantum states that describe the beginning and end of a step in a reaction pathway and at room temperature such intermediate state are usually ground states.</span></span>
<span data-ttu-id="70a36-106">Även om markplanet vanligt vis är för svårt att lära sig (även med en Quantum-dator) eftersom det är en distribution över ett exponentiellt stort antal konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="70a36-106">While the ground state is typically too hard to learn (even with a quantum computer) because it is a distribution over an exponentially large number of configurations.</span></span>
<span data-ttu-id="70a36-107">Det går att lära sig mer om kvantiteter som mark tillstånds energi.</span><span class="sxs-lookup"><span data-stu-id="70a36-107">Quantities such as ground state energy can be learned.</span></span>
<span data-ttu-id="70a36-108">Om t. ex. $ \ket{\psi} $ är ett rent Quantum-tillstånd kommer \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} att ge den genomsnittliga energin som systemet har i detta tillstånd.</span><span class="sxs-lookup"><span data-stu-id="70a36-108">For example, if $\ket{\psi}$ is any pure quantum state then \begin{equation} E = \bra{ \psi } \hat{H} \ket{\psi} \end{equation} gives the mean energy that the system has in that state.</span></span>
<span data-ttu-id="70a36-109">Mark läget är sedan det tillstånd som ger det minsta värdet.</span><span class="sxs-lookup"><span data-stu-id="70a36-109">The ground state then is the state that gives the smallest such value.</span></span> <span data-ttu-id="70a36-110">Därför är det viktigt att välja ett tillstånd som är så nära som möjligt till det verkliga jord läget för att uppskatta energin antingen direkt (som görs i Variations eigensolvers) eller genom fas uppskattning.</span><span class="sxs-lookup"><span data-stu-id="70a36-110">As a result, choosing a state that is as close as possible to the true ground state is vitally important for estimating the energy either directly (as is done in variational eigensolvers) or through phase estimation.</span></span>

<span data-ttu-id="70a36-111">Hartree – Fock teori ger ett enkelt sätt att skapa det ursprungliga läget för Quantum Systems.</span><span class="sxs-lookup"><span data-stu-id="70a36-111">Hartree–Fock theory gives a simple way to construct the initial state for quantum systems.</span></span> <span data-ttu-id="70a36-112">Den ger en enda Slater approximation till ett Quantum-Systems mark tillstånd.</span><span class="sxs-lookup"><span data-stu-id="70a36-112">It yields a single Slater-determinant approximation to the ground state of a quantum system.</span></span> <span data-ttu-id="70a36-113">I detta fall hittar den en rotation i Fock-utrymme som minimerar mark tillståndets energi.</span><span class="sxs-lookup"><span data-stu-id="70a36-113">To that end, it finds a rotation within Fock-space that minimizes the ground state energy.</span></span> <span data-ttu-id="70a36-114">I synnerhet för ett system med $N $ electrons utför metoden rotations \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket {0} \mapsto \ prod_ {j = 0} ^ {N-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket {0} \defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket {0} , \end{Equation} med en anti-Hermitian (dvs. $u =-u ^ \dagger $) matrisen $u = \ sum_ {PQ} u_ {PQ} a ^ \ dagger_p a_q $.</span><span class="sxs-lookup"><span data-stu-id="70a36-114">In particular, for a system of $N$ electrons the method performs the rotation \begin{equation} \prod_{j=0}^{N-1} a^\dagger_j \ket{0} \mapsto \prod_{j=0}^{N-1} e^{u} a^\dagger_j e^{-u} \ket{0}\defeq\prod_{j=0}^{N-1}  \widetilde{a}^\dagger_j  \ket{0}, \end{equation} with an anti-Hermitian (i.e. $u= -u^\dagger$) matrix $u = \sum_{pq} u_{pq} a^\dagger_p a_q$.</span></span> <span data-ttu-id="70a36-115">Det bör noteras att matrisen $u $ representerar orbital-rotationer och $ \widetilde{a} ^ \ dagger_j $ och $ \widetilde{a} _j $ som representerar skapande-och Annihilation-operatörer för electrons som använder Hartree – Fock molekyl ära rotations banor.</span><span class="sxs-lookup"><span data-stu-id="70a36-115">It should be noted that the matrix $u$ represents the orbital rotations and $\widetilde{a}^\dagger_j$ and $\widetilde{a}_j$ represent creation and annihilation operators for electrons occupying Hartree–Fock molecular spin-orbitals.</span></span>


<span data-ttu-id="70a36-116">Matrisen $u $ optimeras sedan för att minimera den förväntade energin $ \bra {0} \ prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \prod \_ {k = 0} ^ {n-1} \widetilde{a} ^ \ dagger_k \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="70a36-116">The matrix $u$ is then optimized to minimize the expected energy $\bra{0} \prod_{j=0}^{N-1}  \widetilde{a}\_j  H \prod\_{k=0}^{N-1}  \widetilde{a}^\dagger_k\ket{0}$.</span></span> <span data-ttu-id="70a36-117">Sådana optimerings problem kan vara generella hårda, i praktiken är Hartree – Fock-algoritmen att snabbt konvergera till en nära optimal lösning på optimerings problemet, särskilt för stängda-Shell-molekyler i jämvikts Geometries.</span><span class="sxs-lookup"><span data-stu-id="70a36-117">While such optimization problems may be generically hard, in practice the Hartree–Fock algorithm tends to rapidly converge to a near-optimal solution to the optimization problem, especially for closed-shell molecules in the equilibrium geometries.</span></span> <span data-ttu-id="70a36-118">Vi kan ange dessa tillstånd som en instans av `FermionWavefunction` objektet.</span><span class="sxs-lookup"><span data-stu-id="70a36-118">We may specify these states as an instance of the `FermionWavefunction` object.</span></span> <span data-ttu-id="70a36-119">Till exempel instansieras tillstånd $a ^ \ dagger_ {1} a ^ \ dagger_ {2} a ^ \ dagger_ {6} \ket {0} $ i kemi-biblioteket på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="70a36-119">For instance, the state $a^\dagger_{1}a^\dagger_{2}a^\dagger_{6}\ket{0}$ is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
<span data-ttu-id="70a36-120">Det är också möjligt att indexera våg funktioner med index `SpinOrbital` och sedan konvertera dessa index till heltal enligt följande.</span><span class="sxs-lookup"><span data-stu-id="70a36-120">It is also possible to index wave functions with `SpinOrbital` indices, and then convert these indices to integers as follows.</span></span>
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="70a36-121">Den mest slående funktionen för Hartree – Fock teori är att den ger ett Quantum-tillstånd som inte har några entanglement mellan electrons.</span><span class="sxs-lookup"><span data-stu-id="70a36-121">The most striking feature about Hartree–Fock theory is that it yields a quantum state that has no entanglement between the electrons.</span></span>
<span data-ttu-id="70a36-122">Det innebär att det ofta finns en lämplig kvalitativ beskrivning av egenskaperna för molekyl system.</span><span class="sxs-lookup"><span data-stu-id="70a36-122">This means that it often provides a suitable qualitative description of properties of molecular systems.</span></span> 

<span data-ttu-id="70a36-123">Hartree-Focks tillstånd kan också rekonstrueras från `FermionHamiltonian`  enligt följande.</span><span class="sxs-lookup"><span data-stu-id="70a36-123">The Hartree-Fock state may also be reconstructed from a `FermionHamiltonian`  as follows.</span></span>
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

<span data-ttu-id="70a36-124">Att få korrekta resultat, särskilt för starkt korrelerade system, kräver dock Quantum-tillstånd som går utöver Hartree – Fock teori.</span><span class="sxs-lookup"><span data-stu-id="70a36-124">However, obtaining accurate results, especially for strongly correlated systems, necessitate quantum states that go beyond Hartree–Fock theory.</span></span>
