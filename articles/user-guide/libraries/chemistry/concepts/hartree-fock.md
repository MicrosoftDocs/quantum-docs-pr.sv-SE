---
title: Hartree – Fock teori
description: Lär dig mer om Hartree – Fock teori, ett enkelt sätt att skapa det ursprungliga läget för Quantum Systems.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275950"
---
# <a name="hartreefock-theory"></a>Hartree – Fock teori

Kanske är den viktigaste mängden i Quantum kemi-simuleringen jord, vilket är den minsta energi eigenvector i Hamiltonian-matrisen.
Detta beror på att för de flesta molekylerna vid rums temperatur, till exempel reaktions taxan, domineratss genom kostnads fria energi skillnader mellan Quantum-tillstånd som beskriver början och slutet av ett steg i en reaktions väg och vid rums temperatur är det vanligt vis jord tillstånd.
Även om markplanet vanligt vis är för svårt att lära sig (även med en Quantum-dator) eftersom det är en distribution över ett exponentiellt stort antal konfigurationer.
Det går att lära sig mer om kvantiteter som mark tillstånds energi.
Om t. ex. $ \ket{\psi} $ är ett rent Quantum-tillstånd kommer \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} att ge den genomsnittliga energin som systemet har i detta tillstånd.
Mark läget är sedan det tillstånd som ger det minsta värdet. Därför är det viktigt att välja ett tillstånd som är så nära som möjligt till det verkliga jord läget för att uppskatta energin antingen direkt (som görs i Variations eigensolvers) eller genom fas uppskattning.

Hartree – Fock teori ger ett enkelt sätt att skapa det ursprungliga läget för Quantum Systems. Den ger en enda Slater approximation till ett Quantum-Systems mark tillstånd. I detta fall hittar den en rotation i Fock-utrymme som minimerar mark tillståndets energi. I synnerhet för ett system med $N $ electrons utför metoden rotations \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket {0} \mapsto \ prod_ {j = 0} ^ {N-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket {0} \defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket {0} , \end{Equation} med en anti-Hermitian (dvs. $u =-u ^ \dagger $) matrisen $u = \ sum_ {PQ} u_ {PQ} a ^ \ dagger_p a_q $. Det bör noteras att matrisen $u $ representerar orbital-rotationer och $ \widetilde{a} ^ \ dagger_j $ och $ \widetilde{a} _j $ som representerar skapande-och Annihilation-operatörer för electrons som använder Hartree – Fock molekyl ära rotations banor.


Matrisen $u $ optimeras sedan för att minimera den förväntade energin $ \bra {0} \ prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \prod \_ {k = 0} ^ {n-1} \widetilde{a} ^ \ dagger_k \ket {0} $. Sådana optimerings problem kan vara generella hårda, i praktiken är Hartree – Fock-algoritmen att snabbt konvergera till en nära optimal lösning på optimerings problemet, särskilt för stängda-Shell-molekyler i jämvikts Geometries. Vi kan ange dessa tillstånd som en instans av `FermionWavefunction` objektet. Till exempel instansieras tillstånd $a ^ \ dagger_ {1} a ^ \ dagger_ {2} a ^ \ dagger_ {6} \ket {0} $ i kemi-biblioteket på följande sätt.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
Det är också möjligt att indexera våg funktioner med index `SpinOrbital` och sedan konvertera dessa index till heltal enligt följande.
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

Den mest slående funktionen för Hartree – Fock teori är att den ger ett Quantum-tillstånd som inte har några entanglement mellan electrons.
Det innebär att det ofta finns en lämplig kvalitativ beskrivning av egenskaperna för molekyl system. 

Hartree-Fock-tillstånd kan också rekonstrueras från en `FermionHamiltonian` som följer.
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

Att få korrekta resultat, särskilt för starkt korrelerade system, kräver dock Quantum-tillstånd som går utöver Hartree – Fock teori.
