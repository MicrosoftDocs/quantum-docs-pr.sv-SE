---
title: Korrelerade vågfunktioner
description: Lär dig om dynamiska och icke-dynamiska korrelationer i wavefunctions med Microsoft Quantum kemi-biblioteket.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
ms.openlocfilehash: 005ef86382ca72969b06a4206cab01f3845718e2
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275914"
---
# <a name="correlated-wavefunctions"></a>Korrelerade vågfunktioner

För många system, särskilt de nära jämvikts geometrin, ger [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) teori en kvalitativ beskrivning av molekyl egenskaper genom ett engångs referens tillstånd. Men för att uppnå kvantitativ noggrannhet måste det också ta hänsyn till korrelations effekter. 

I det här sammanhanget är det viktigt att dinstinguish mellan dynamiska och icke-dynamiska korrelationer.
Det uppstår dynamiska korrelationer från tendensen av electrons för att hålla isär, till exempel på grund av en interelektronisk drivning. Den här funktionen kan utformas genom att man överväger excitations av electrons. Icke-dynamiska korrelationer uppstår när wavefunction är dominerats av två eller flera konfigurationer i Zeroth-ordning, även om du bara vill uppnå en kvalitativ beskrivning av systemet.
Detta kräver en överplacering av Determinant och är ett exempel på en wavefunction med multireferens.

Kemi-biblioteket är ett sätt att ange en Zeroth order-wavefunction för ett multireferens-problem som en överplacering av Determinant. Den här metoden, som vi kallar sparse multireference wavefunctions, är effektiv när bara några få komponenter räcker för att ange överplacering. Biblioteket innehåller också en metod för att inkludera dynamiska korrelationer ovanpå en engångs referens via den generaliserade enhetliga kluster ansatz. Dessutom konstrueras även Quantum-kretsar som genererar dessa tillstånd på en Quantum-dator. Dessa tillstånd kan anges i Broombridge- [schemat](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)och vi tillhandahåller även funktionen för att manuellt ange dessa tillstånd via kemi-biblioteket.

## <a name="sparse-multi-reference-wavefunction"></a>Wavefunction för sparse-flera referenser
En \ket{\ för flera referenser $ psi_ {\rm {MCSCF}}} $ kan anges explicit som en linjär kombination av $N $-Electron Slater determininants.
\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots a ^ \ dagger_ {i_N} \ket {0} .
\end{align} t. ex. State $ \propto (0,1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ kan anges i kemi-biblioteket på följande sätt.
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
Den här explicita representationen av superpositions komponenterna är effektiv när bara några få komponenter behöver anges. Du bör undvika att använda den här representationen när många komponenter krävs för att korrekt kunna avbilda det önskade läget. Anledningen är att den här gaten är en Quantum-krets som förbereder det här läget på en Quantum-dator, som skalas minst linjärt med antalet superpositions komponenter och som är mest kvadratiskt med en-norm för amplituderna superposition.

## <a name="unitary-coupled-cluster-wavefunction"></a>Enhetligt kluster wavefunction
Det är också möjligt att ange en enhetlig, fristående kluster wavefunction $ \ket{\ psi_ {\rm {UCC}}} $ med chemistery-biblioteket. I den här situationen har vi ett engångs referens tillstånd, t. ex. $ \ket{\ psi_ {\rm{SCF}}} $. Komponenterna i den enhetliga kluster wavefunction anges sedan som implicit genom en enhetlig operatör som agerar i ett referens tillstånd.
Den här enhetliga operatorn skrivs vanligt vis som $e ^ {T-T ^ \dagger} $, där $T-T ^ \dagger $ är den Hermitian kluster operatorn. Därför \begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.
\end{align}

Det är också vanligt att dela upp kluster operatorn $T = T_1 + T_2 + \cdots $ i delar, där varje del $T _j $ innehåller $j $-Body-villkor. I generaliserad kluster teori är Singles (Enbody Cluster-operatören) av formatet \begin{align} T_1 = \ sum_ {PQ} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}

och två huvud kluster operatörer (dubbla) har formatet \begin{align} T_2 = \ sum_ {PQRS} T ^ {PQ} _ {RS} a ^ \ dagger_p a ^ \ dagger_q a_r a_s.
\end{align}

Högre ordning (tredubbla, fyr dubbels osv.) är möjliga, men stöds för närvarande inte av kemi-biblioteket.

Låt säga att $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} $ och låt $T = 0,123 a ^ \ dagger_0 A_1 + 0,456 a ^ \ dagger_0a ^ \ dagger_3 a_1 a_2-0,789 a ^ \ dagger_3a ^ \ dagger_2 A_1 a_0 $. Sedan instansieras det här läget i kemi-biblioteket på följande sätt.
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

Rotations convervation kan göras explicit genom att i stället ange `SpinOrbital` index i stället för heltals index. Låt säga att $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} a ^ \ dagger_ {2, \downarrow}\ket {0} $ och låt $T = 0,123 a ^ \ dagger_ {0, \uparrow} a_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} a_ {1, \uparrow} a_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ convserving. Sedan instansieras det här läget i kemi-biblioteket på följande sätt.
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

Vi tillhandahåller också en bekvämlighets funktion som räknar upp över alla konversation kluster operatörer som Annihilate endast upptagna varv-och glädjer-funktioner.
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