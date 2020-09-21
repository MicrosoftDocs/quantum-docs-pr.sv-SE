---
title: Inbyggda funktioner och funktioner i QDK
description: Lär dig mer om de inbyggda funktionerna och funktionerna i QDK, inklusive funktioner för klassisk verksamhet, rotation och mätning.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.prelude
no-loc:
- Q#
- $$v
ms.openlocfilehash: dd507d0c644ae711a5e5a1dff9156f571cb0fa92
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833545"
---
# <a name="the-prelude"></a>Inledning #

Q#Kompilatorn och mål datorerna som ingår i Quantum Development Kit innehåller en uppsättning inbyggda funktioner och åtgärder som kan användas när du skriver Quantum-program i Q# .

## <a name="intrinsic-operations-and-functions"></a>Inbyggda funktioner och funktioner ##

De inbyggda åtgärder som definieras i standard biblioteket är i stort sett en av flera kategorier:

- Grundläggande klassiska funktioner som samlas in i <xref:microsoft.quantum.core> namn området.
- Åtgärder som representerar unitaries som består av [Clifford och $T $ Gates](xref:microsoft.quantum.concepts.qubit).
- Åtgärder som representerar rotationer om olika operatorer.
- Åtgärder som implementerar mätningar.

Eftersom port uppsättningen Clifford + $T $ är [universell](xref:microsoft.quantum.concepts.multiple-qubits) för Quantum Computing, räcker dessa åtgärder för att implementera alla Quantum-algoritmer inom försumbart litet fel.
Genom att tillhandahålla rotationer kan Q# programmeraren fungera i ett enda qubit-port bibliotek med CNOT. Det här biblioteket är mycket enklare att tänka på eftersom programmeraren inte behöver uttrycka Clifford + $T $-dekompositionen och eftersom det finns mycket effektiva metoder för att kompilera enskilda qubit-unitaries i Clifford och $T $ Gates (mer information finns [här](xref:microsoft.quantum.more-information) ).

Där det är möjligt kan de åtgärder som definierats i inledning som agerar på qubits tillåta att använda `Controlled` varianten, så att mål datorn utför lämplig dekomposition.

Många av de funktioner och åtgärder som definierats i den här delen av inledning finns i @"microsoft.quantum.intrinsic" namn området, så att de flesta Q# källfiler har ett `open Microsoft.Quantum.Intrinsic;` direktiv direkt efter den inledande namn rymds deklarationen.
<xref:microsoft.quantum.core>Namn området öppnas automatiskt, så att funktioner som <xref:microsoft.quantum.core.length> kan användas utan någon `open` instruktion alls.

### <a name="common-single-qubit-unitary-operations"></a>Vanliga åtgärder med en enda qubit ###

Inledning definierar också många vanliga [qubit-åtgärder](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).
Alla dessa åtgärder tillåter både- `Controlled` och `Adjoint` functors.

#### <a name="pauli-operators"></a>Pauli-operatörer ####

<xref:microsoft.quantum.intrinsic.x>Åtgärden implementerar Pauli $X $-operatorn.
Detta kallas ibland även för `NOT` porten.
Den har signatur `(Qubit => Unit is Adj + Ctl)` .
Det motsvarar en qubit:

\begin{Equation} \begin{bmatrix} 0 & 1 \\ \\ % fixme: för närvarande används quadwhack hackare.
1 & 0 \end{bmatrix} \end{Equation}

<xref:microsoft.quantum.intrinsic.y>Åtgärden implementerar Pauli $Y $-operatorn.
Den har signatur `(Qubit => Unit is Adj + Ctl)` .
Det motsvarar en qubit:

\begin{Equation} \begin{bmatrix} 0 &-i \\ \\ % fixme: för närvarande används quadwhack Hack.
Jag & 0 \end{bmatrix} \end{Equation}

<xref:microsoft.quantum.intrinsic.z>Åtgärden implementerar Pauli $Z $-operatorn.
Den har signatur `(Qubit => Unit is Adj + Ctl)` .
Det motsvarar en qubit:

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: för närvarande används quadwhack hackare.
0 &-1 \end{bmatrix} \end{Equation}

Nedan visas dessa omvandlingar som är kopplade till [Bloch-sfären](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (rotations axeln i varje fall är markerad som röd):

![Pauli-åtgärder som har mappats till Bloch-sfären](~/media/prelude_pauliBloch.png)

Det är viktigt att Observera att att tillämpa samma Pauli-grind två gånger på samma qubit avbryter åtgärden (eftersom du nu har utfört en fullständig rotation av 2π (360 °) över ytan till Bloch-sfären, och därmed kommer tillbaka vid start punkten). Detta ger oss följande identitet:

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

Detta kan vara visualised på Bloch-sfären:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Annan qubit Cliffords ####

<xref:microsoft.quantum.intrinsic.h>Åtgärden implementerar Hadamard-porten.
Detta förändrar Pauli-$X $ och $Z $-axlarna i mål qubit, till exempel $H \ket {0} = \ket{+} \mathrel{: =} (\ket {0} + \ket {1} )/\sqrt {2} $ och $H \ket{+} = \ket {0} $.
Den innehåller en signatur `(Qubit => Unit is Adj + Ctl)` och motsvarar den enda-qubit-enhetliga:

\begin{Equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % fixme: för närvarande används quadwhack hacka.
1 &-1 \end{bmatrix} \end{Equation}

Hadamard-porten är särskilt viktig eftersom den kan användas för att skapa en superposition för $ \ket {0} $ och $ \ket {1} $. I sfär representationen Bloch är det enklast att tänka på detta som en rotation av $ \ket{\psi} $ runt x-axeln med $ \pi $ radianer ($ 180 ^ \circ $) följt av en rotation på y-axeln med $ \ Pi/2 $ radianer ($ 90 ^ \circ $):

![Hadamard-åtgärd mappad till Bloch-sfären](~/media/prelude_hadamardBloch.png)

<xref:microsoft.quantum.intrinsic.s>Åtgärden implementerar fas porten $S $.
Detta är matrisen för matrisen Pauli $Z $.
Det vill säga $S ^ 2 = Z $.
Den innehåller en signatur `(Qubit => Unit is Adj + Ctl)` och motsvarar den enda-qubit-enhetliga:

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: för närvarande används quadwhack hackare.
0 & i \end{bmatrix}-\end{Equation}

#### <a name="rotations"></a>Rotationer ####

Utöver Pauli-och Clifford-åtgärderna ovan Q# tillhandahåller inledning en mängd olika sätt att uttrycka rotationer.
Som beskrivs i [en qubit-åtgärd](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)är möjligheten att rotera kritiskt för Quantum-algoritmer.

Vi börjar med att komma ihåg att vi kan uttrycka en enskild qubit-åtgärd med hjälp av $H $ och $T $-grindarna, där $H $ är Hadamard-åtgärden och där \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ % fixme: det här använder för närvarande Whack hackare.
0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} detta är kvadratroten av <xref:microsoft.quantum.intrinsic.s> åtgärden, till exempel $T ^ 2 = S $.
$T $-porten implementeras av <xref:microsoft.quantum.intrinsic.t> åtgärden och har en signatur som `(Qubit => Unit is Adj + Ctl)` anger att det är en enhetlig åtgärd på en enskild-qubit.

Även om detta är i princip tillräckligt för att beskriva en godtycklig enskild qubit-åtgärd kan olika mål datorer ha mer effektiva representationer för rotationer om Pauli-operatörer, till exempel att inledning innehåller en mängd olika sätt att convienently Express sådana rotationer.
De flesta av dessa är <xref:microsoft.quantum.intrinsic.r> åtgärden, som implementerar en rotation runt en angiven Pauli-axel, \Begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation} där $ \sigma $ är en Pauli-operatör, $ \phi $ är en vinkel och där $ \exp $ representerar matrisen exponent.
Den innehåller en signatur `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` där de första två delarna i indatamängden representerar de klassiska argumenten $ \sigma $ och $ \phi $ som krävs för att ange den enhetliga operatorn $R (\sigma, \phi) $.
Vi kan delvis använda $ \sigma $ och $ \phi $ för att få en åtgärd vars typ är en enda-qubit-enhetlig.
Har till exempel `R(PauliZ, PI() / 4, _)` typen `(Qubit => Unit is Adj + Ctl)` .

> [!NOTE]
> <xref:microsoft.quantum.intrinsic.r>Åtgärden delar upp ingångs vinkeln med 2 och multiplicerar den med-1.
> För $Z $-rotationer innebär detta att $ \ket {0} $ eigenstate roteras av $-\phi/$2 och att $ \ket {1} $ eigenstate roteras med $ \phi/$2, så att $ \ket {1} $ eigenstate roteras med $ \phi $ i förhållande till $ \ket {0} $ eigenstate.
>
> Detta innebär särskilt att `T` och `R(PauliZ, PI() / 8, _)` bara skiljer sig från en irrelevant [Global fas](xref:microsoft.quantum.glossary#global-phase).
> Av den anledningen kallas $T $ $ \frac{\pi} {8} $-grind.
>
> Observera också att när du roterar runt `PauliI` bara tillämpas en global fas av $ \phi/$2. Även om dessa faser är irrelevanta, så som vi anförde i [de konceptuella dokumenten](xref:microsoft.quantum.concepts.qubit), är de relevanta för kontrollerade `PauliI` rotationer.

I Quantum-algoritmer är det ofta användbart att uttrycka rotationer som dyadic bråktal, till exempel $ \phi = \pi k/2 ^ n $ för vissa $k \in \mathbb{Z} $ och $n \in \mathbb{N} $.
<xref:microsoft.quantum.intrinsic.rfrac>Åtgärden implementerar en rotation runt en angiven Pauli axel med denna konvention.
Det skiljer sig från <xref:microsoft.quantum.intrinsic.r> i att rotations vinkeln har angetts som två indata av typen `Int` , tolkas som en dyadic fraktion.
Därför `RFrac` har signatur `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` .
Den implementerar en qubit-\exp (i \pi k \sigma/2 ^ n) $, där $ \sigma $ är den Pauli matris som motsvarar det första argumentet, $k $ är det andra argumentet och $n $ är det tredje argumentet.
`RFrac(_,k,n,_)` är detsamma som `R(_,-πk/2^n,_)` . Observera att vinkeln är *negativ* för bråket.

<xref:microsoft.quantum.intrinsic.rx>Åtgärden implementerar en rotation runt Pauli-$X $-axeln.
Den har signatur `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rx(_, _)` är samma som `R(PauliX, _, _)` .

<xref:microsoft.quantum.intrinsic.ry>Åtgärden implementerar en rotation runt Pauli-$Y $-axeln.
Den har signatur `((Double, Qubit) => Unit is Adj + Ctl)` .
`Ry(_, _)` är samma som `R(PauliY,_ , _)` .

<xref:microsoft.quantum.intrinsic.rz>Åtgärden implementerar en rotation runt Pauli-$Z $-axeln.
Den har signatur `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rz(_, _)` är samma som `R(PauliZ, _, _)` .

<xref:microsoft.quantum.intrinsic.r1>Åtgärden implementerar en rotation med den mängd som finns runt $ \ket {1} $, $-$1-eigenstate för $Z $.
Den har signatur `((Double, Qubit) => Unit is Adj + Ctl)` .
`R1(phi,_)` är detsamma som `R(PauliZ,phi,_)` följt av `R(PauliI,-phi,_)` .

<xref:microsoft.quantum.intrinsic.r1frac>Åtgärden implementerar en fraktions rotation med den mängd som finns runt Z = 1-eigenstate.
Den har signatur `((Int,Int, Qubit) => Unit is Adj + Ctl)` .
`R1Frac(k,n,_)` är detsamma som `RFrac(PauliZ,-k.n+1,_)` följt av `RFrac(PauliI,k,n+1,_)` .

Ett exempel på en rotations åtgärd (runt Pauli $Z $-axeln, i den här instansen) som är mappad till Bloch-sfären visas nedan:

![Rotations åtgärd som är mappad till Bloch-sfären](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Multi-qubit-åtgärder ####

Förutom de enskilda qubit-åtgärderna ovan definierar inledning också flera åtgärder för flera qubit.

Först <xref:microsoft.quantum.intrinsic.cnot> utför åtgärden en kontrollerad- `NOT` grind, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & \\ \\ 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}.
\end{Equation} den har signatur `((Qubit, Qubit) => Unit is Adj + Ctl)` , som representerar $ \operatorname{CNOT} $ agerar unitarily på två enskilda qubits.
`CNOT(q1, q2)` är samma som `(Controlled X)([q1], q2)` .
Eftersom `Controlled` Functor gör det möjligt att kontrol lera ett register använder vi mat ris strängen `[q1]` för att indikera att vi bara vill ha den enda kontrollen.

<xref:microsoft.quantum.intrinsic.ccnot>Åtgärden utför dubblerad-styrd icke-grind, ibland även kallat Toffoli-porten.
Den har signatur `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` .
`CCNOT(q1, q2, q3)` är samma som `(Controlled X)([q1, q2], q3)` .

<xref:microsoft.quantum.intrinsic.swap>Åtgärden byter ut Quantum-tillstånden för två qubits.
Det innebär att den implementerar den enhetliga matrisen \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}.
\end{Equation} den har signatur `((Qubit, Qubit) => Unit is Adj + Ctl)` .
`SWAP(q1,q2)` motsvarar `CNOT(q1, q2)` följt av `CNOT(q2, q1)` och sedan `CNOT(q1, q2)` .

> [!NOTE]
> VÄXLINGs porten är *inte* samma sak som att ordna om elementen i en variabel med typ `Qubit[]` .
> `SWAP(q1, q2)`Att tillämpa gör en ändring i status för den qubits som refereras till av `q1` och `q2` , men `let swappedRegister = [q2, q1];` påverkar bara hur vi refererar till dessa qubits.
> Dessutom `(Controlled SWAP)([q0], (q1, q2))` gör det möjligt `SWAP` att villkorligt godkännas för en tredje qubit, som vi inte kan representera genom att arrangera om element.
> Den övervakade VÄXLINGs porten, som även kallas Fredkin-grind, är tillräckligt kraftfull för att inkludera all klassisk beräkning.

Slutligen tillhandahåller inledning två åtgärder för att representera exponenter för multi-qubit Pauli-operatörer.
<xref:microsoft.quantum.intrinsic.exp>Åtgärden utför en rotation baserat på en behållen produkt i Pauli-matriser. som representeras av multi-qubit-\Begin{Equation} \operatorname{exp} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), \end{Equation} där $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ är en följd av en vinkel.
`Exp`Rotationen representerar $ \vec{\sigma} $ som en matris med `Pauli` element, till exempel signaturen `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .

<xref:microsoft.quantum.intrinsic.expfrac>Åtgärden utför samma rotation med dyadic bråk notationen som beskrivs ovan.
Den har signatur `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` .

> [!WARNING]
> Pauli-operatörernas exponenter är inte samma som för bevarans produkter av Pauli-operatörernas exponenter.
> Det vill säga $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.

### <a name="measurements"></a>Mått ###

Vid mätningen motsvarar + 1-eigenvalue för den operator som mäts till ett `Zero` resultat och eigenvalue-1-till ett `One` resultat.

> [!NOTE]
> Även om denna konvention kan verka ojämn, har den två mycket bra fördelar.
> För det första visas resultatet $ \ket {0} $ av `Result` värdet `Zero` , samtidigt som $ \ket {1} $ motsvarar `One` .
> Sedan kan vi skriva ut att eigenvalue $ \lambda $ som motsvarar resultatet $r $ är $ \lambda = (-1) ^ r $.

Mått åtgärder stöder varken `Adjoint` eller `Controlled` Functor.

<xref:microsoft.quantum.intrinsic.measure>Åtgärden utför en gemensam mätning av en eller flera qubits i den angivna produkten av Pauli-operatörer.
Om Pauli-matrisen och qubit-matrisen har olika längd, Miss lyckas åtgärden.
`Measure` har signatur `((Pauli[], Qubit[]) => Result)` .

Observera att en gemensam mätning inte är samma som att mäta varje qubit individuellt.
Anta till exempel tillstånd $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $.
Mätning $Z _0 $ och $Z _1 $ var för sig får du resultaten $r _0 = $1 och $r _1 = $1.
Mätning $Z _0 Z_1 $, men vi får ett enda resultat $r _ {\textrm{joint}} = $0, som visar att paret $ \ket {11} $ är positivt.
Sätt på olika sätt, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}}) $.
Eftersom vi *bara* lär dig paritet från den här mätningen bevaras alla Quantum-uppgifter som representeras i superpositionen mellan 2 2-qubit-tillstånden för positiv paritet, $ \ket {00} $ och $ \ket {11} $.
Den här egenskapen är viktig senare, eftersom vi diskuterar fel korrigering.

För enkelhetens skull tillhandahåller inledning också två andra åtgärder för att mäta qubits.
För det första, eftersom det är ganska vanligt att utföra qubit mätningar definierar inledning en kort skrift för det här fallet.
<xref:microsoft.quantum.intrinsic.m>Åtgärden mäter Pauli $Z $-operatorn på en enskild qubit och har signatur `(Qubit => Result)` .
`M(q)` motsvarar `Measure([PauliZ], [q])` .

<xref:microsoft.quantum.measurement.multim>Måtten Pauli $Z $-operatören *var separat* på var och en av qubits, och returnerar *matrisen* med `Result` värden som hämtats för varje qubit.
I vissa fall kan detta optimeras. Den har signatur ( `Qubit[] => Result[])` .
`MultiM(qs)` motsvarar:

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a>Funktioner och åtgärder för tillägg ##

Dessutom definierar inledning en omfattande uppsättning matematiska och typ konverterings funktioner på .NET-nivå för användning i Q# kod.
Till exempel <xref:microsoft.quantum.math> definierar namn området användbara åtgärder som <xref:microsoft.quantum.math.sin> och <xref:microsoft.quantum.math.log> .
Den implementering som tillhandahålls av Quantum Development Kit använder det klassiska .NET-klass biblioteket och kan därmed omfatta en ytterligare överföring av kommunikation mellan Quantum-program och deras klassiska driv rutiner.
Även om detta inte visar något problem för en lokal simulator kan detta vara ett prestanda problem när du använder en fjärrsimulator eller en faktisk maskin vara som mål dator.
I detta fall kan en enskild måldator minimera den här prestanda påverkan genom att åsidosätta dessa åtgärder med versioner som är mer effektiva för det specifika systemet.

### <a name="math"></a>Matematik ###

<xref:microsoft.quantum.math>Namn området innehåller många användbara funktioner i .NET Base Class-bibliotekets [ `System.Math` klass](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true).
Dessa funktioner kan användas på samma sätt som andra Q# funktioner:

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

Om en statisk metod för .NET har överlagrats baserat på typen av argument, Q# är motsvarande funktion kommenterad med ett suffix som anger indatatypen:

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Bitvisa åtgärder ###

Slutligen <xref:microsoft.quantum.bitwise> tillhandahåller namn området flera användbara funktioner för att manipulera heltal genom bitvisa operatorer.
Returnerar till exempel <xref:microsoft.quantum.bitwise.parity> den bitvisa pariteten för ett heltal som ett heltal.
