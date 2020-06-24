---
title: Andra kvantifieringsfel
description: Lär dig mer om den andra kvantifieringsfel-metoden för att utforma elektroniska strukturer i Quantum-programmering.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: e17c97767b05395af46a82c4035337406c7e3218
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276112"
---
# <a name="second-quantization"></a>Andra kvantifieringsfel

Andra kvantifieringsfel tittar på problemet med elektronisk struktur via en annan lins.
I stället för att tilldela var och en av de $N _e $ electrons till ett särskilt tillstånd (eller orbital), spårar andra kvantifieringsfel varje orbital och lagrar om det finns en Electron som finns på var och en av dem och samtidigt säkerställer egenskaperna för den motsvarande Wave-funktionens symmetri egenskaper automatiskt.
Detta är viktigt eftersom det gör det möjligt att ange Quantum kemi-modeller utan att behöva oroa sig för att symmetrizing ingångs tillstånd (som krävs för Fermions) och även om andra kvantifieringsfel tillåter att sådana modeller simuleras med hjälp av små quantum datorer.

Som ett exempel på andra kvantifieringsfel i praktiken antar vi att $ \ psi_0 \cdots \ psi_ {N-1} $ är en orthonormal uppsättning med avstånd för överbanor.
Dessa insikter väljs för att representera systemet så korrekt som möjligt inom den begränsade bas uppsättningen som beaktas.
Ett vanligt exempel på sådana banor är atomiska banor som bildar en eigenbasis för väte-Atomen.
Eftersom electrons har två varv tillstånd kan två electrons vara Crammed i varje sådan spatiala orbital.
Det vill säga att giltiga bas tillstånd är av typen $ \ psi_ {0, \uparrow}, \ldots, \ psi_ {N-1, \uparrow}, \ psi_ {0, \downarrow}, \ldots, \ psi_ {N-1, \downarrow} $ där $ \uparrow $ och $ \downarrow $ är etiketter som anger de två eigenstates i rotations graden.
Det här kombinerade indexet $ (j, \sigma) $ för $ \sigma \in \{ \uparrow, \downarrow \} $ kallas för ett rotations-orbital eftersom det lagrar både spatialdata och rotations graden för frihet.
I kemi-biblioteket lagras rotations-banor i en `SpinOrbital` data struktur och skapas på följande sätt.

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

Det innebär att vi kan formellt tänka på grund för både rotations-och rums delen av vågen som $ \ psi_ {0} \cdots \ psi_ {2n-1} $ där var och en av indexen nu är en uppräkning av en $ (j, \sigma) $.
En möjlig uppräkning är $g (j, \sigma) = j + N\sigma $.
En annan möjlig uppräkning är $h (j, \sigma) = 2 * j + \sigma $.
Quantum kemi-biblioteket kan använda dessa konventioner och rotations banaarna i en sådan kodning kan instansieras på följande sätt.

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

För fermionic-system förhindrar Pauli uteslutnings principen att fler än en Electron förekommer i en rotations-orbital på samma tidpunkt.
Det innebär att vi kan skriva de två juridiska tillstånden för $ \ psi_1 $ som \begin{Equation} \ psi_1 \rightarrow \begin{Cases} \ket {0} _1 & \text{IF $ \ psi_1 $ inte är upptagna,}\\\
\ket {1} _1 & \text{IF $ \ psi_1 $ är upptagen.} \end{Cases} \end{Equation} den här kodningen är perfekt för Quantum Computers eftersom det innebär att vi kan lagra den elektroniska yrket som en enda Quantum-bit.

Yrkes tillstånden för $2N $-rotations banorna kan liknas på samma sätt i $2N $ qubits.
Exempel: om $N = $2 sedan tillstånd $ $ \ket {0} \ket {1} \ket {1} \ket {0} , $ $

motsvarar rotations banaarna $1 $ och $2 $ som är upptagna med resten tom.
På samma sätt är tillstånd $ $ \ket {0} \equiv \ket {0} _ {0} \cdots \ket {0} _{N-1}, $ $

har ingen electrons och kallas vakuum-tillstånd.

En snygg sido effekt av andra kvantifieringsfel är att vi inte längre behöver hålla koll på antisymmetrin i Quantum-tillstånd.
Detta beror på att, som vi kommer att se, är antisymmetrin av statusen i stället i stället för de ansvariga operatörernas regler för att skapa och förstöra elektroniska yrken i ett varv orbital.

## <a name="fermionic-operators"></a>Fermionic-operatörer

De två grundläggande operatörerna som fungerar på de andra quantized-bas vektorerna kallas skapande-och Annihilation-operatörer.
Dessa operatörer infogar eller förstör electrons på en viss plats.
Dessa betecknas $a ^ \ dagger_j $ och $a _j $ respektive.

Till exempel \begin{align} a ^ \ dagger_1 \ket {0} _1 = \ket {1} _1, \quad a ^ \ dagger_1 \ket {1} _1 = 0, \quad A_1 \ket {0} _1 = 0, \quad A_1 \ket {1} _1 = \ket {0} _1.
\end{align} Obs! här $a ^ \ dagger_1 \ket {1} _1 = 0 $ och $a _1 \ket {0} _1 $ ger noll-Vector inte $ \ket {0} _1 $.
Sådana operatörer är därför varken Hermitiana eller på samma sätt.
Vi representerar allmänna skapande-och Annihilation-operatörer med hjälp av <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> typen.
En enda skapande operator visas till exempel som följer.

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

Även med sådana operatörer kan vi uttrycka $ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} ^ {\otimes 4}.
$ $ Den här sekvensen av operatörer skulle konstrueras i biblioteket för Hamiltonian-simulering med C#-kod som liknar orbital med ett enda varv som anses ovan:
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

För ett system med $k $ Fermions, i andra kvantifieringsfel, har åtgärden att skapa operatör $a ^ \ dagger_i $ angetts av $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $ $ och $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, $ $ där $S _i = \ sum_ {j<i} a ^ \ dagger_j a_j $ mäter det totala antalet Fermions som är i samma tillstånd som en enskild partikel och som har ett index $j < i $.

En tredje operator används också ofta i andra quantized-representationer.
Den här operatorn kallas för nummer operatorn och definieras av \begin{Equation} n_i = a ^ \ dagger_i a_i.
\end{Equation} den här operatorn räknar om en specifik orbital, vilket är att säga \begin{align} n_i \ket {0} _i &= 0 \ nonumber\\\
n_i \ket {1} _i &= \ket {1} _i.
\end{align} som liknar ovanstående `FermionTerm` exempel skapas den här nummer operatorn enligt följande.
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

En subtlety uppstår även när du använder skapande-eller Annihilation-operatörer i fermionic-system.
Vi kräver att alla giltiga Quantum-tillstånd är antisymmetriska i utbyte av etiketter.
Det innebär att $ $ a ^ \ dagger_2 a ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} .
$ $ Sådana operatörer säger att "anti-arbets" och allmänt för alla $i, j $ har \begin{align} a ^ \ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) a ^ \ dagger_j a ^ \ dagger_i, \quad a ^ \ dagger_i a_j = \ delta_ {i, j} – a_j a ^ \ dagger_i.
\end{align} därför betraktas följande två <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instanser som likvärdiga
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

Kravet på att var och en av de skapande operatörerna använder en andra quantized-representation gör så utmaningar med Fermions.
I stället visas utmaningen på nytt i vår definition av de skapande operatörerna. 

Med hjälp av regler för att koppla från regler `LadderSequence` motsvarar vissa instanser faktiskt samma sekvens av fermionic-operatörer, ibland upp till ett minus tecken.
Anta till exempel att Hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $.
Detta motiverar oss att definiera en kanonisk ordning för var och en `FermionTerm` .
Alla sätts `FermionTerm` automatiskt in i den kanoniska ordningen enligt följande.
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

## <a name="second-quantized-fermionic-hamiltonian"></a>Andra – quantized Fermionic-Hamiltonian

Det är kanske unsurprising att Hamiltonian i [Quantum-modeller för elektroniska system](xref:microsoft.quantum.chemistry.concepts.quantummodels) kan skrivas i form av skapande-och Annihilation-operatörer.
I synnerhet, om $ \psi \_ j $ är de rotations banor som utgör grunden

\begin{Equation} \hat{H} = \sum \_ {PQ} H \_ {PQ} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {PQRS} H \_ {PQRS} a ^ \dagger \_ p a ^ \dagger \_ q a \_ ra \_ s + h \_ {\textrm NUC}, \label{EQ: totalHam} \end{Equation} där $h \_ {\Textrm NUC} $ är kärn energin (som är konstant under den födda-Oppenheimer-uppskattningen) och

\begin{align} h \_ {PQ} &= \int \_ {-\infty} ^ \infty \psi ^ \* \_ p (x \_ 1) \left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \psi \_ q (x \_ 1) \mathrm{d} ^ 3x \_ 1, \end{align}

där $V (x) $ är potentialen medel fält och

\begin{align} h \_ {PQRS} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \psi \_ q ^ \* (x \_ 2) \left (\frac {1} {| x_1-x_2 |} \right) \psi \_ r (x \_ 2) \psi \_ s (x \_ 1) \mathrm{d} ^ 3x \_ 1 \ mathrm {d} ^ 3x \_ 2. \ Label {EQ: integraler} \end{align}

Termerna $h \_ {PQ} $ kallas en-Electron integraler eftersom alla sådana termer bara omfattar enskilda electrons och även $h \_ {PQRS} $ är de två Electron integralerna.
De kallas integraler eftersom beräkning av värdena för dessa koefficienter kräver en integral.
Det enda villkoret för Electron beskriver den enskilda electrons och deras interaktioner med de elektriska fälten i kärnor.
De två Electron-integralerna å andra sidan beskriver interaktionerna mellan electrons.

En intuition för det här villkoret kan vara uppnår från skapande-och Annihilation-operatörerna som omfattar var och en av dem.
Exempel: $h _ {PQ} a ^ \ dagger_p a_q $ beskriver Electron hoppande från rotation orbital $q $ för att snurra orbital $p $.
På samma sätt beskriver termen $h _ {PQRS} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (för distinkta $p, q, r, s $) två electrons i rotations banaarna $r $ och $s $-spridning av varandra och du avslutar i rotations banorna $p $ och $q $.
Om $r = q $ och $p = s $ sedan $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ ger den energi påföljd som är kopplad till de två electrons nära varandra, men beskriver inte en dynamisk process.

Vi kan representera sådana Hamiltonians med hjälp av `FermionHamiltonian` klassen, som är i grunden en lista som innehåller alla önskade `FermionTerm` instanser.
Eftersom Hamiltonians är Hermitian definitions mässigt indexerar vi termerna med hjälp av en mer specialiserad typ `HermitianFermionTerm` som också använder Hermitian-symmetri när de kontrollerar om villkoren är likvärdiga.

Låt oss skapa några exempel på exempel.
Överväg Hamiltonian $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $.
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
Vi kan förenkla denna konstruktion med det faktum att Hamiltonian-operatörer är Hermitian-operatörer.
När du lägger till villkor i Hamiltonian med `Add` , antas alla icke-Hermitian, till exempel, `fermionTerm0` kombineras med dess Hermitian-konjugat.
Följande kodfragment representerar därför också samma Hamiltonian:
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

Med hjälp av regler för att koppla från regler, `FermionTerm` motsvarar vissa instanser i Hamiltonian samma sekvens med fermionic-operatörer, ibland upp till ett minus tecken.
Anta till exempel att Hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $, som är en summa av de termer som skapats ovan.
Det är inte alltid uppenbart att användaren har motsvarande villkor, och därför kan de läggas till i Hamiltonian separat.
Det kan också vara intressant att ändra redan befintliga termer i Hamiltonian.
I dessa fall kan vi kombinera motsvarande termer på följande sätt.
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
Genom att kombinera koefficienter med likvärdiga villkor minskar vi det totala antalet villkor i Hamiltonian.
Senare, minskar detta antalet Quantum-grindar som krävs för att simulera Hamiltonian.

### <a name="internal-representation"></a>Intern representation

En fermionic-Hamiltonian med en och två-Body-interaktioner visas i quantized-notation som

$ $ \begin{align} H = \sum \_ {PQ} H \_ {PQ} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {PQRS} H \_ {PQRS} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a { \_ r} a \_ {s}.
\end{align} $ $

I det här formatet finns högst $N ^ 2 + N ^ 4 $ koefficienter.
Många av dessa koefficienter kan dock samlas in när de motsvarar samma operatör.
Till exempel, i fall där $p, q, r, s $ är distinkta index, vi kan använda regler för att se till att: $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger \_ {p} a { \_ r} a { \_ s} =-a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {s} a { \_ r} = a ^ \dagger \_ {q} a ^ \dagger \_ {p} a { \_ \_ r}.
$$

Dessutom är $H $ Hermitian, varje icke-Hermitian fermionic-Operator, säg $h \_ {PQRS} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a {r} a {s} \_ \_ $, har ett Hermitian-konjugat som också finns i $H $. För att unikt indexera grupper av termer som karakteriseras av dessa symmetries, vi definierar en kanonisk ordning på indexen $ (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) $ i en sekvens med $n + m $ fermionic-operatörer $a ^ \dagger \_ {i \_ 1} \cdots a ^ \dagger \_ {i \_ n} a \_ {j \_ 1} \cdots a \_ {j \_ m} $as följande:
-   Alla operatorer för skapande $a ^ \dagger \_ {i \_ \cdot} $ placeras före alla Annihilation-operatörer $a \_ {j \_ \cdot} $.
-   Alla index för skapande operatorer sorteras i stigande ordning, vilket är $i \_ 1< i \_ 2< \cdots < i \_ n $.
-   Alla index för Annihilation-operatorer sorteras i fallande ordning, det vill säga $j \_ 1> j \_ 2 \cdots > j \_ m $.
-   Det vänstra indexet är mindre än eller lika med det högra indexet, det vill säga $i \_ 1 \ Le j \_ m $.

Låt oss identifiera den här uppsättningen av kanoniskt sorterade index som $ $ \begin{align} (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) \in S \_ {n, m}.
\end{align} $ $

Med den här kanoniska ordningen kan fermionic-Hamiltonian uttryckas som $ $ \begin{align} H = \sum \_ {(p, q) \In S \_ {1,1} } H ' \_ {PQ} \frac{a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger \_ {q} a \_ {p}} {2} + \sum \_ {(p, q, r, s) \in s \_ {2,2} } H \_ {PQRS} \frac{a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {S} + a ^ \dagger \_ {S} a ^ \dagger \_ {r} a \_ {q} a \_ {p}} {2} , \end{align} $ $ med lämpligt anpassat en-och två Electron-integraler $h \_ {PQ} $ och $h \_ {PQRS} $.

