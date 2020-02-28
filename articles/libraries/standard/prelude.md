---
title: Inbyggda funktioner och funktioner i QDK
description: Lär dig mer om de inbyggda funktionerna och funktionerna i QDK, inklusive funktioner för klassisk verksamhet, rotation och mätning.
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b1c26c632f36b6c254d940a89b13638f7592ab80
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907213"
---
# <a name="the-prelude"></a>Inledning #

Q #-kompilatorn och mål datorerna som ingår i Quantum Development Kit innehåller en uppsättning inbyggda funktioner och åtgärder som kan användas när du skriver Quantum-program i Q #.

## <a name="intrinsic-operations-and-functions"></a>Inbyggda funktioner och funktioner ##

De inbyggda åtgärder som definieras i standard biblioteket är i stort sett en av flera kategorier:

- Viktiga klassiska funktioner som samlas in i <xref:microsoft.quantum.core>-namnrymden.
- Åtgärder som representerar unitaries som består av [Clifford och $T $ Gates](xref:microsoft.quantum.concepts.qubit).
- Åtgärder som representerar rotationer om olika operatorer.
- Åtgärder som implementerar mätningar.

Eftersom port uppsättningen Clifford + $T $ är [universell](xref:microsoft.quantum.concepts.multiple-qubits) för Quantum Computing, räcker dessa åtgärder för att implementera alla Quantum-algoritmer inom försumbart litet fel.
Genom att tillhandahålla rotationer kan du också använda Q # för att programmerare ska fungera inom ett enda qubit-port bibliotek med CNOT. Det här biblioteket är mycket enklare att tänka på eftersom programmeraren inte behöver uttrycka Clifford + $T $-dekompositionen och eftersom det finns mycket effektiva metoder för att kompilera enskilda qubit-unitaries i Clifford och $T $ Gates (mer information finns [här](xref:microsoft.quantum.more-information) ).

Där det är möjligt kan de åtgärder som definierats i inledning, som agerar på qubits, använda den `Controlled` varianten, så att mål datorn utför lämplig dekomposition.

Många av de funktioner och åtgärder som definierats i den här delen av inledning finns i @"microsoft.quantum.intrinsic" namn området, så att de flesta Q # källfiler kommer att ha ett `open Microsoft.Quantum.Intrinsic;`-direktiv omedelbart efter den inledande namn rymds deklarationen.
<xref:microsoft.quantum.core> namn området öppnas automatiskt, så att funktioner som <xref:microsoft.quantum.core.length> kan användas utan ett `open`-uttryck alls.

### <a name="common-single-qubit-unitary-operations"></a>Vanliga åtgärder med en enda qubit ###

Inledning definierar också många vanliga [qubit-åtgärder](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).
Alla dessa åtgärder tillåter både `Controlled` och `Adjoint` functors.

#### <a name="pauli-operators"></a>Pauli-operatörer ####

Åtgärden <xref:microsoft.quantum.intrinsic.x> implementerar Pauli $X $-operatorn.
Detta kallas ibland även `NOT`-porten.
Signaturen `(Qubit => Unit is Adj + Ctl)`.
Det motsvarar en qubit:

\begin{Equation} \begin{bmatrix} 0 & 1 \\\\% FIXME: för närvarande används quadwhack Hack.
1 & 0 \end{bmatrix} \end{Equation}

Åtgärden <xref:microsoft.quantum.intrinsic.y> implementerar Pauli $Y $-operatorn.
Signaturen `(Qubit => Unit is Adj + Ctl)`.
Det motsvarar en qubit:

\begin{Equation} \begin{bmatrix} 0 &-i \\\\% FIXME: för närvarande används quadwhack Hack.
Jag & 0 \end{bmatrix} \end{Equation}

Åtgärden <xref:microsoft.quantum.intrinsic.z> implementerar Pauli $Z $-operatorn.
Signaturen `(Qubit => Unit is Adj + Ctl)`.
Det motsvarar en qubit:

\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: för närvarande används quadwhack Hack.
0 &-1 \end{bmatrix} \end{Equation}

Nedan visas dessa omvandlingar som är kopplade till [Bloch-sfären](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (rotations axeln i varje fall är markerad som röd):

![Pauli-åtgärder som har mappats till Bloch-sfären](~/media/prelude_pauliBloch.png)

Det är viktigt att Observera att att tillämpa samma Pauli-grind två gånger på samma qubit avbryter åtgärden (eftersom du nu har utfört en fullständig rotation av 2π (360 °) över ytan till Bloch-sfären, och därmed kommer tillbaka vid start punkten). Detta ger oss följande identitet:

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

Detta kan vara visualised på Bloch-sfären:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Annan qubit Cliffords ####

<xref:microsoft.quantum.intrinsic.h>-åtgärden implementerar Hadamard-porten.
Detta förändrar Pauli $X $ och $Z $-axlarna i mål qubit, till exempel $H \ket{0} = \ket{+} \mathrel{: =} (\ket{0} + \ket{1})/\sqrt{2}$ och $H \ket{+} = \ket{0}$.
Den har signatur `(Qubit => Unit is Adj + Ctl)`och motsvarar den enda-qubit-enhetliga:

\begin{Equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\% FIXME: för närvarande används quadwhack hacka.
1 &-1 \end{bmatrix} \end{Equation}

Hadamard-porten är särskilt viktig eftersom den kan användas för att skapa en superposition för $ \ket-{0}$ och $ \ket{1}$. I sfär representationen Bloch är det enklast att tänka på detta som en rotation av $ \ket{\psi} $ runt x-axeln med $ \pi $ radianer ($ 180 ^ \circ $) följt av en rotation på y-axeln med $ \ Pi/2 $ radianer ($ 90 ^ \circ $):

![Hadamard-åtgärd mappad till Bloch-sfären](~/media/prelude_hadamardBloch.png)

<xref:microsoft.quantum.intrinsic.s> åtgärden implementerar fas porten $S $.
Detta är matrisen för matrisen Pauli $Z $.
Det vill säga $S ^ 2 = Z $.
Den har signatur `(Qubit => Unit is Adj + Ctl)`och motsvarar den enda-qubit-enhetliga:

\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: för närvarande används quadwhack Hack.
0 & i \end{bmatrix}-\end{Equation}

#### <a name="rotations"></a>Rotation ####

Utöver Pauli-och Clifford-åtgärderna ovan tillhandahåller Q # inledning en mängd olika sätt att uttrycka rotationer.
Som beskrivs i [en qubit-åtgärd](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)är möjligheten att rotera kritiskt för Quantum-algoritmer.

Vi börjar med att komma ihåg att vi kan uttrycka en enskild-qubit-åtgärd med hjälp av $H $ och $T $ Gates, där $H $ är Hadamard-åtgärden och där \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\\\% FIXME: det här använder för närvarande Whack Hack.
0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} detta är kvadratroten av <xref:microsoft.quantum.intrinsic.s> åtgärden, till exempel $T ^ 2 = S $.
$T $-porten implementeras i sin tur av <xref:microsoft.quantum.intrinsic.t>-åtgärden och har signatur `(Qubit => Unit is Adj + Ctl)`, vilket indikerar att det är en enhetlig åtgärd på en enskild-qubit.

Även om detta är i princip tillräckligt för att beskriva en godtycklig enskild qubit-åtgärd kan olika mål datorer ha mer effektiva representationer för rotationer om Pauli-operatörer, till exempel att inledning innehåller en mängd olika sätt att convienently uttrycka sådana rotationer.
De flesta av dessa är <xref:microsoft.quantum.intrinsic.r> åtgärden, som implementerar en rotation runt en angiven Pauli-axel, \begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation} där $ \sigma $ är en Pauli-operatör, $ \phi $ är en vinkel och där $ \exp $ representerar matrisen exponentiell.
Signaturen `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, där de första två delarna av indatamängden representerar de klassiska argumenten $ \sigma $ och $ \phi $ som krävs för att ange den enhetliga operatorn $R (\sigma, \phi) $.
Vi kan delvis använda $ \sigma $ och $ \phi $ för att få en åtgärd vars typ är en enda-qubit-enhetlig.
`R(PauliZ, PI() / 4, _)` har till exempel typen `(Qubit => Unit is Adj + Ctl)`.

> [!NOTE]
> Åtgärden <xref:microsoft.quantum.intrinsic.r> delar upp ingångs vinkeln med 2 och multiplicerar den med-1.
> För $Z $-rotationer innebär detta att $ \ket{0}$ eigenstate roteras av $-\phi/$2 och $ \ket{1}$ eigenstate roteras med $ \phi/$2, så att $ \ket{1}$ eigenstate roteras med $ \phi $ i förhållande till $ \ket{0}$ eigenstate.
>
> Det innebär framför allt att `T` och `R(PauliZ, PI() / 8, _)` bara skiljer sig från en irrelevant [Global fas](xref:microsoft.quantum.glossary#global-phase).
> Av den anledningen kallas $T $ $ \frac{\pi}{8}$-grind.
>
> Observera också att när du roterar runt `PauliI` tillämpas bara en global fas av $ \phi/$2. Även om dessa faser är irrelevanta, som vi gjorde i [de konceptuella dokumenten](xref:microsoft.quantum.concepts.qubit), är de relevanta för kontrollerade `PauliI` rotationer.

I Quantum-algoritmer är det ofta användbart att uttrycka rotationer som dyadic bråktal, till exempel $ \phi = \pi k/2 ^ n $ för vissa $k \in \mathbb{Z} $ och $n \in \mathbb{N} $.
<xref:microsoft.quantum.intrinsic.rfrac> åtgärden implementerar en rotation runt en angiven Pauli axel med hjälp av denna konvention.
Det skiljer sig från <xref:microsoft.quantum.intrinsic.r> i att rotations vinkeln har angetts som två indata av typen `Int`, tolkas som en dyadic fraktion.
`RFrac` har därför signatur `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.
Den implementerar en qubit-\exp (i \pi k \sigma/2 ^ n) $, där $ \sigma $ är den Pauli matris som motsvarar det första argumentet, $k $ är det andra argumentet och $n $ är det tredje argumentet.
`RFrac(_,k,n,_)` är samma som `R(_,-πk/2^n,_)`. Observera att vinkeln är *negativ* för bråket.

<xref:microsoft.quantum.intrinsic.rx> åtgärden implementerar en rotation runt Pauli $X $-axeln.
Signaturen `((Double, Qubit) => Unit is Adj + Ctl)`.
`Rx(_, _)` är samma som `R(PauliX, _, _)`.

<xref:microsoft.quantum.intrinsic.ry> åtgärden implementerar en rotation runt Pauli $Y $-axeln.
Signaturen `((Double, Qubit) => Unit is Adj + Ctl)`.
`Ry(_, _)` är samma som `R(PauliY,_ , _)`.

<xref:microsoft.quantum.intrinsic.rz> åtgärden implementerar en rotation runt Pauli $Z $-axeln.
Signaturen `((Double, Qubit) => Unit is Adj + Ctl)`.
`Rz(_, _)` är samma som `R(PauliZ, _, _)`.

<xref:microsoft.quantum.intrinsic.r1> åtgärden implementerar en rotation efter den mängd som finns runt $ \ket{1}$, $-$1-eigenstate för $Z $.
Signaturen `((Double, Qubit) => Unit is Adj + Ctl)`.
`R1(phi,_)` är samma som `R(PauliZ,phi,_)` följt av `R(PauliI,-phi,_)`.

<xref:microsoft.quantum.intrinsic.r1frac>-åtgärden implementerar en fraktions rotation med den mängd som finns runt Z = 1-eigenstate.
Signaturen `((Int,Int, Qubit) => Unit is Adj + Ctl)`.
`R1Frac(k,n,_)` är samma som `RFrac(PauliZ,-k.n+1,_)` följt av `RFrac(PauliI,k,n+1,_)`.

Ett exempel på en rotations åtgärd (runt Pauli $Z $-axeln, i den här instansen) som är mappad till Bloch-sfären visas nedan:

![Rotations åtgärd som är mappad till Bloch-sfären](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Multi-qubit-åtgärder ####

Förutom de enskilda qubit-åtgärderna ovan definierar inledning också flera åtgärder för flera qubit.

Först utför <xref:microsoft.quantum.intrinsic.cnot> åtgärden en standard styrd-`NOT`-grind, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.
\end{Equation} den har signatur `((Qubit, Qubit) => Unit is Adj + Ctl)`, som representerar $ \operatorname{CNOT} $ agerar unitarily på två enskilda qubits.
`CNOT(q1, q2)` är samma som `(Controlled X)([q1], q2)`.
Eftersom `Controlled` Functor gör det möjligt att kontrol lera ett register använder vi mat ris strängen `[q1]` för att indikera att vi bara vill ha den enda kontrollen.

<xref:microsoft.quantum.intrinsic.ccnot> åtgärden utför dubbelriktad-kontrollerad icke-grind, ibland även kallad Toffoli-porten.
Signaturen `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.
`CCNOT(q1, q2, q3)` är samma som `(Controlled X)([q1, q2], q3)`.

Med åtgärden <xref:microsoft.quantum.intrinsic.swap> byter du Quantum-tillstånden för två qubits.
Det innebär att det implementerar den enhetliga matrisen \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.
\end{Equation} har signaturen `((Qubit, Qubit) => Unit is Adj + Ctl)`.
`SWAP(q1,q2)` motsvarar `CNOT(q1, q2)` följt av `CNOT(q2, q1)` och `CNOT(q1, q2)`sedan.

> [!NOTE]
> VÄXLINGs porten är *inte* samma sak som att ordna om elementen i en variabel med typen `Qubit[]`.
> Om du använder `SWAP(q1, q2)` ändras statusen för den qubits som refereras till av `q1` och `q2`, medan `let swappedRegister = [q2, q1];` bara påverkar hur vi refererar till dessa qubits.
> Dessutom tillåter `(Controlled SWAP)([q0], (q1, q2))` att `SWAP` villkorligt för en tredje qubit, som vi inte kan representera genom att arrangera om element.
> Den övervakade VÄXLINGs porten, som även kallas Fredkin-grind, är tillräckligt kraftfull för att inkludera all klassisk beräkning.

Slutligen tillhandahåller inledning två åtgärder för att representera exponenter för multi-qubit Pauli-operatörer.
<xref:microsoft.quantum.intrinsic.exp>-åtgärden utför en rotation baserat på en behållen produkt av Pauli-matriser. som representeras av multi-qubit-\begin{Equation} \operatorname{Exp} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), \end{Equation} där $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ är en följd av en vinkel.
`Exp` rotationen representerar $ \vec{\sigma} $ som en matris med `Pauli` element, t. ex. signaturen `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.

<xref:microsoft.quantum.intrinsic.expfrac>-åtgärden utför samma rotation med dyadic bråk notationen som beskrivs ovan.
Signaturen `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.

> [!WARNING]
> Pauli-operatörernas exponenter är inte samma som för bevarans produkter av Pauli-operatörernas exponenter.
> Det vill säga $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.

### <a name="measurements"></a>Mått ###

Vid mätningen motsvarar de + 1 eigenvalue i operatorn som mäts till ett `Zero` resultat och eigenvalue-1-till ett `One` resultat.

> [!NOTE]
> Även om denna konvention kan verka ojämn, har den två mycket bra fördelar.
> Först och med att observera resultatet $ \ket{0}$ representeras av `Result` värde `Zero`, samtidigt som $ \ket{1}$ motsvarar `One`.
> Sedan kan vi skriva ut att eigenvalue $ \lambda $ som motsvarar resultatet $r $ är $ \lambda = (-1) ^ r $.

Mått åtgärder stöder varken `Adjoint` eller `Controlled` Functor.

<xref:microsoft.quantum.intrinsic.measure> åtgärden utför en gemensam mätning av en eller flera qubits i den angivna produkten av Pauli-operatörer.
Om Pauli-matrisen och qubit-matrisen har olika längd, Miss lyckas åtgärden.
`Measure` har signatur `((Pauli[], Qubit[]) => Result)`.

Observera att en gemensam mätning inte är samma som att mäta varje qubit individuellt.
Anta till exempel tillstånd $ \ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.
Mätning $Z _0 $ och $Z _1 $ var för sig får du resultaten $r _0 = $1 och $r _1 = $1.
Mätning $Z _0 Z_1 $, men vi får ett enda resultat $r _ {\textrm{joint}} = $0, som visar att \ket för ${11}$ är positiv.
Sätt på olika sätt, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}}) $.
Eftersom vi *bara* lär dig paritet från den här mätningen bevaras alla Quantum-uppgifter som representeras i superpositionen mellan 2 2-qubit-tillstånden för positiv paritet, $ \ket{00}$ och $ \ket{11}$.
Den här egenskapen är viktig senare, eftersom vi diskuterar fel korrigering.

För enkelhetens skull tillhandahåller inledning också två andra åtgärder för att mäta qubits.
För det första, eftersom det är ganska vanligt att utföra qubit mätningar definierar inledning en kort skrift för det här fallet.
Åtgärden <xref:microsoft.quantum.intrinsic.m> mäter Pauli $Z $-operatorn på en enskild qubit och har signatur `(Qubit => Result)`.
`M(q)` motsvarar `Measure([PauliZ], [q])`.

<xref:microsoft.quantum.measurement.multim> mäter Pauli $Z $-operatören *separat* på var och en av qubits, och returnerar *matrisen* med `Result` värden som hämtats för varje qubit.
I vissa fall kan detta optimeras. Den har signatur (`Qubit[] => Result[])`.
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

Dessutom definierar inledning en omfattande uppsättning matematiska och typ konverterings funktioner på .NET-nivån för användning inom Q # Code.
Till exempel definierar <xref:microsoft.quantum.extensions.math>-namnrymden användbara åtgärder som <xref:microsoft.quantum.extensions.math.sin> och <xref:microsoft.quantum.extensions.math.log>.
Den implementering som tillhandahålls av Quantum Development Kit använder det klassiska .NET-klass biblioteket och kan därmed omfatta en ytterligare överföring av kommunikation mellan Quantum-program och deras klassiska driv rutiner.
Även om detta inte visar något problem för en lokal simulator kan detta vara ett prestanda problem när du använder en fjärrsimulator eller en faktisk maskin vara som mål dator.
I detta fall kan en enskild måldator minimera den här prestanda påverkan genom att åsidosätta dessa åtgärder med versioner som är mer effektiva för det specifika systemet.

### <a name="math"></a>Uttrycket ###

<xref:microsoft.quantum.extensions.math>-namnrymden innehåller många användbara funktioner från [`System.Math`s klass](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)i .NET Base-klassens bibliotek.
Dessa funktioner kan användas på samma sätt som andra Q #-funktioner:

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

Om en statisk metod för .NET har överlagrats baserat på typen av argument är motsvarande Q #-funktion kommenterad med ett suffix som anger indatatypen:

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Bitvisa åtgärder ###

Slutligen tillhandahåller <xref:microsoft.quantum.extensions.bitwise>-namnrymden flera användbara funktioner för att manipulera heltal genom bitvisa operatorer.
<xref:microsoft.quantum.extensions.bitwise.parity> returnerar till exempel den bitvisa pariteten för ett heltal som ett heltal.
