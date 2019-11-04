---
title: Hartree – Fock teori | Microsoft Docs
description: Hartree – Fock teori-dokument
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: e73111ae710e11ca6730581b8be711cf32783677
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184108"
---
# <a name="hartreefock-theory"></a>Hartree – Fock teori

Kanske är den viktigaste mängden i Quantum kemi-simuleringen jord, vilket är den minsta energi eigenvector i Hamiltonian-matrisen.
Detta beror på att för de flesta molekyler i rums temperatur, till exempel reaktions taxan, domineratss genom kostnads fria energi skillnader mellan Quantum-tillstånd som beskriver början och slutet av ett steg i en reaktions väg och vid rums temperatur, sådan mellanliggande State är vanligt vis jord tillstånd.
Även om markplanet vanligt vis är för svårt att lära sig (även med en Quantum-dator) eftersom det är en distribution över ett exponentiellt stort antal konfigurationer.
Det går att lära sig mer om kvantiteter som mark tillstånds energi.
Om t. ex. $ \ket{\psi} $ är ett rent Quantum-tillstånd kommer \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} att ge den genomsnittliga energin som systemet har i detta tillstånd.
Mark läget är sedan det tillstånd som ger det minsta värdet. Därför är det viktigt att välja ett tillstånd som är så nära som möjligt till det verkliga jord läget för att uppskatta energin antingen direkt (som görs i Variations eigensolvers) eller genom fas uppskattning.

Hartree – Fock teori ger ett enkelt sätt att skapa det ursprungliga läget för Quantum Systems. Den ger en enda Slater approximation till ett Quantum-Systems mark tillstånd. I detta fall hittar den en rotation i Fock-utrymme som minimerar mark tillståndets energi. I synnerhet, för ett system med $N $ electrons, utför metoden rotations \begin{Equation} \prod_{j = 0} ^ {N-1} a ^ \dagger_j \ket{0} \mapsto \prod_{j = 0} ^ {N-1} e ^ {u} a ^ \dagger_j e ^ {-u} \ket{0}\defeq\prod_{j = 0} ^ {N-1} \widetilde{a} ^ \dagger _J \ket{0}, \end{Equation} med en anti-Hermitian (t. ex. $u =-u ^ \dagger $) Matrix $u = \sum_{PQ} u_ {PQ} a ^ \dagger_p a_q $. Det bör noteras att matrisen $u $ representerar orbital-rotationer och $ \widetilde{a} ^ \dagger_j $ och $ \widetilde{a}_J $ som representerar skapande och Annihilation operatörer för electrons som använder Hartree – Fock molekyl ära rotations banor.


Matrisen $u $ optimeras sedan för att minimera den förväntade energi $ \bra{0} \prod_{j = 0} ^ {N-1} \widetilde{a}\_j H \prod\_{k = 0} ^ {N-1} \widetilde{a} ^ \dagger_k\ket{0}$. Sådana optimerings problem kan vara generella hårda, i praktiken är Hartree – Fock-algoritmen att snabbt konvergera till en nära optimal lösning på optimerings problemet, särskilt för stängda-Shell-molekyler i jämvikts Geometries. Vi kan ange dessa tillstånd som en instans av `FermionWavefunction`-objektet. Till exempel är tillstånd $a ^ \dagger_{1}en ^ \dagger_{2}a ^ \dagger_{6}\ket{0}$ instansieras i kemi-biblioteket på följande sätt.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
Det går också att indexera våg funktioner med `SpinOrbital` index och sedan konvertera dessa index till heltal enligt följande.
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

Hartree-Fock-tillstånd kan också rekonstrueras från en `FermionHamiltonian` enligt följande.
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

Att få korrekta resultat, särskilt för starkt korrelerade system, kräver dock Quantum-tillstånd som går utöver Hartree – Fock teori.