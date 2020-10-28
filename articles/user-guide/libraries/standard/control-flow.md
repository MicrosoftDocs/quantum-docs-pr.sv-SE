---
title: Flödes kontroller i Q# standard libararies
description: Lär dig mer om flödes kontroll åtgärder och funktioner i Microsoft Q# standard-biblioteket.
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: ad107f5c65a4bf368d12d30e4a72786f2076205c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690864"
---
# <a name="higher-order-control-flow"></a>Higher-Order kontroll flöde #

En av de primära rollerna i standard biblioteket är att göra det enklare att uttrycka algoritmiska idéer på hög nivå som [Quantum-program](https://en.wikipedia.org/wiki/Quantum_programming).
Q#Canon tillhandahåller därför en mängd olika konstruktioner för flödes kontroll, som var och en implementeras med hjälp av delvis tillämpning av funktioner och åtgärder.
Hoppa direkt till ett exempel, Tänk på i vilket fall ett som vill skapa en "CNOT-steg" i ett register:

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

Vi kan uttrycka det här mönstret genom att använda iterationer och `for` slingor:

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

Uttryckt i form av <xref:Microsoft.Quantum.Canon.ApplyToEachCA> och mat ris manipulations funktioner, till exempel, <xref:Microsoft.Quantum.Arrays.Zipped> är det mycket kortare och lättare att läsa:

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

I resten av det här avsnittet kommer vi att tillhandahålla ett antal exempel på hur du använder de olika flödes styrnings åtgärder och-funktioner som tillhandahålls av Canon för att komprimera Express Quantum-program.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Använda åtgärder och funktioner över matriser och intervall ##

En av de primära abstraktionerna från Canon är den iterationen.
Anta till exempel att du har en enhetlig utformning av formuläret $U \otimes U \otimes \cdots \otimes U $ för en enda qubit-$U $.
I kan Q# vi använda <xref:Microsoft.Quantum.Arrays.IndexRange> för att representera detta som en `for` slinga över ett register:

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

Vi kan sedan använda den nya åtgärden som `HAll(register)` att tillämpa $H \Otimes h \otimes \cdots \Otimes h $.

Detta är besvärligt att göra, särskilt i en större algoritm.
Den här metoden är dessutom specialiserad på den särskilda åtgärd som vi vill tillämpa på varje qubit.
Vi kan använda det faktum att åtgärder är första klass för att uttrycka det här algoritmiska konceptet uttryckligen:

```qsharp
ApplyToEachCA(H, register);
```

Här anger suffixet `CA` att anropet till `ApplyToEach` är adjointable och kontrollerbar.
Om `U` stöder `Adjoint` och `Controlled` , är följande rader likvärdiga:

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

Det innebär särskilt att anrop till `ApplyToEachCA` kan visas i åtgärder för vilka en angränsande specialisering genereras automatiskt.
På samma sätt <xref:Microsoft.Quantum.Canon.ApplyToEachIndex> är det bra att representera mönster i formuläret `U(0, targets[0]); U(1, targets[1]); ...` och erbjuder versioner för varje kombination av functors som stöds av indata.

> [!TIP]
> `ApplyToEach` är typ-parameterad så att den kan användas med åtgärder som tar andra indata än `Qubit` .
> Anta till exempel att `codeBlocks` är en matris med <xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister> värden som behöver återställas.
> Sedan `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` kommer att använda fel korrigerings kod `code` och återställnings funktion `recoveryFn` för varje block oberoende av varandra.
> Detta omfattar även för klassiska indata: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` en rotation på $ \pi/$2 om $X $ följt av en rotation på $Pi/$3 om $Y $.

Q#Canon har även stöd för klassiska uppräknings mönster som är bekanta med funktions programmering.
Implementera till exempel <xref:Microsoft.Quantum.Arrays.Fold> mönstret $f (f (f (s \_ {\text{initial}}, x \_ 0), x \_ 1), \dots) $ för att minska en funktion över en lista.
Det här mönstret kan användas för att implementera summor, produkter, minimi, maximal och andra funktioner:

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

På samma sätt kan funktioner som <xref:Microsoft.Quantum.Arrays.Mapped> och <xref:Microsoft.Quantum.Arrays.MappedByIndex> användas för att uttrycka funktionella programmerings koncept i Q# .

## <a name="composing-operations-and-functions"></a>Skapa åtgärder och funktioner ##

De kontroll flödes konstruktioner som tillhandahålls av Canon utför åtgärder och fungerar som indata, så att det är bra att kunna skapa flera åtgärder eller funktioner i ett enda anrop.
Mönstret $UVU ^ {\dagger} $ är till exempel mycket vanligt i Quantum-programmering, så att Canon tillhandahåller åtgärden <xref:Microsoft.Quantum.Canon.ApplyWith> som en abstraktion för det här mönstret.
Den här abstraktionen gör det också möjligt att effektivt följa kretsar, eftersom det `Controlled` inte behöver vidta några åtgärder på grund av sekvensen `U(qubit); V(qubit); Adjoint U(qubit);` `U` .
Vi kan se detta genom att låta $c (U) $ vara den enhetliga som representerar `Controlled U([control], target)` och låta $c (V) $ definieras på samma sätt.
För ett godtyckligt tillstånd $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \OTIMES (uvu ^ {\dagger} \ket{\psi}) \\ \\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes u ^ \dagger) \ket {1} \otimes \ket{\psi}.
\end{align} enligt definitionen av `Controlled` .
Å andra sidan, \begin{align} c (U) c (V) c (U) ^ \dagger \ket {0} \otimes \ket{\psi} & = \ket \otimes {0} \ket{\psi} \\ \\ & = \ket {0} \otimes (UU ^ \dagger \ket{\psi}) \\ \\ & = (\Boldone \otimes u) (c (v)) (\boldone \otimes u ^ \dagger) \ket {0} \otimes \ket{\psi}.
\end{align} med linjäritet kan vi säga att vi kan räkna $U $ på det här sättet för alla ingångs tillstånd.
Det vill säga $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.
Eftersom styrnings åtgärder kan vara dyra i allmänhet, använder kontrollerade varianter som `WithC` och `WithCA` kan hjälpa till att minska antalet kontroll functors som behöver tillämpas.

> [!NOTE]
> En annan följd av utjämningen $U $ är att vi inte behöver ens veta hur du tillämpar `Controlled` Functor på `U` .
> `ApplyWithCA` har därför en svagare signatur än vad som kan förväntas:
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

På samma sätt <xref:Microsoft.Quantum.Canon.Bound> skapar åtgärder som tillämpar en sekvens av andra åtgärder i tur och ordning.
Till exempel motsvarar följande:

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

Att kombinera med upprepnings mönster kan göra detta särskilt användbart:

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Time-Ordered sammansättning ###

Vi kan gå vidare ytterligare genom att tänka på flödes kontroll i termer av partiella program och klassiska funktioner, och kan modellera ännu ganska avancerade Quantum-koncept vad gäller klassisk flödes kontroll.
Den här analoga delen görs exakt genom igenkänningen att de enhetliga operatörerna motsvarar sidans effekter av anrops åtgärder, till exempel att eventuell nedbrytning av enhetliga operatörer i termer av andra enhetliga operatörer motsvarar att skapa en särskild anrops ordning för klassiska under rutiner som genererar instruktioner för att agera som specifika enhetliga operatörer.
I den här vyn `Bound` är en exakt representation av mat ris produkten, eftersom `Bound([A, B])(target)` motsvarar `A(target); B(target);` , vilket i sin tur är den anrops ordning som motsvarar $ba $.

Ett mer avancerat exempel är [Trotter – Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).
Som det beskrivs i avsnittet om åter givning av dynamisk Generator i [data strukturer](xref:microsoft.quantum.libraries.data-structures), är Trotter – Suzuki-expansion ett särskilt användbart sätt att uttrycka mat ris exponenter.
Om du till exempel använder utökningen i den lägsta ordern ger alla operatörer $A $ och $B $ sådana $A = A ^ \dagger $ och $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (in A t/n) \exp (i B t/n) \right) ^ n.
\end{align} colloquially, vi säger att vi kan ungefär utveckla ett tillstånd under $A + B $ genom en annan utveckling under $A $ och $B $ ensamt.
Om vi representerar utvecklingen under $A $ med en åtgärd `A : (Double, Qubit[]) => Unit` som gäller $e ^ {i t A} $, blir åter givningen av Trotter – Suzuki-expansionen i termer av att ordna om anrops sekvenser tydlig.
Konkret, med tanke på en åtgärd `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` som `A = U(0, _, _)` och `B = U(1, _, _)` , kan vi definiera en ny åtgärd som representerar integralen av `U` vid tiden $t $ genom att generera sekvenser av formuläret

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

Nu kan vi nu vara orsaken till Trotter – Suzuki-expansionen *utan referens till Quantum Mechanics* .
Expansionen är i praktiken ett särskilt upprepnings mönster som är motiverat av $ \eqref{EQ: Trotter-Suzuki-0} $.
Detta upprepnings mönster implementeras av <xref:Microsoft.Quantum.Canon.DecomposedIntoTimestepsCA> :

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

Signaturen för `DecomposeIntoTimeStepsCA` följer ett vanligt mönster i Q# , där samlingar som kan säkerhets kopie ras antingen av matriser eller av något som beräknar element i farten representeras av tupler vars första element är `Int` värden som anger deras längd.

## <a name="putting-it-together-controlling-operations"></a>Placera det tillsammans: styra åtgärder ##

Dessutom bygger Canon på `Controlled` Functor genom att tillhandahålla ytterligare sätt att utvärdera Quantum-åtgärder.
Det är vanligt, särskilt i Quantum-aritmetiskt, till villkors åtgärder i andra beräknings underlag än $ \ket{0\cdots 0} $.
Med hjälp av de kontroll åtgärder och funktioner som introducerades ovan kan vi använda mer generella Quantum villkor i ett enda uttryck.
Nu ska vi gå vidare till hur <xref:Microsoft.Quantum.Canon.ControlledOnBitString> ser det (San-typ parametrar). sedan kommer vi att dela upp delarna en i taget.
Det första vi behöver göra är att definiera en åtgärd som faktiskt utför den stora avläsningen av genomförandet av kontrollen i godtyckliga beräknings bas tillstånd.
Vi kommer inte att anropa den här åtgärden direkt, men vi lägger till `_` i början av namnet för att ange att det är en implementering av en annan konstruktion någon annan stans.

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

Observera att vi tar en sträng med bitar, som visas som en `Bool` matris, som vi använder för att ange det villkor som vi vill tillämpa på den åtgärd `oracle` som vi har fått.
Eftersom den här åtgärden faktiskt gör programmet direkt, behöver vi också ta kontroll-och mål registren, som båda visas här som `Qubit[]` .

Nu noterar vi att du har kontroll över beräknings bas tillstånd $ \ket{\vec{s}} = \ket{s \_ 0 s \_ 1 \dots s \_ {n-1}} $ för en bit sträng $ \vec{s} $ kan realiseras genom att omvandla $ \ket{\vec{s}} $ till $ \ket{0\cdots 0} $.
I synnerhet $ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{0\cdots 0} $.
Eftersom $X ^ {\dagger} = X $, innebär detta att $ \ket{0\dots 0} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{\vec{s}} $.
Därför kan vi använda $P = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} $, tillämpa `Controlled oracle` och omvandla tillbaka till $ \vec{s} $.
Den här konstruktionen är exakt `ApplyWith` , så vi skriver texten i vår nya åtgärd i enlighet med detta:

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

Här har vi använt <xref:Microsoft.Quantum.Canon.ApplyPauliFromBitString> för att tillämpa $P $, som delvis använder sig av målet för användning med `ApplyWith` .
Observera dock att vi behöver omvandla *kontroll* registret till vårt önskade formulär, så vi använder delvis den inre åtgärden `(Controlled oracle)` på *målet* .
Detta `ApplyWith` gör att du får en parentes för kontroll registret med $P $, precis som vi vill.

Vi kan nu vara klara, men det tar på sig att inte uppfylla den nya åtgärden, som att använda `Controlled` Functor.
Vi slutför därför att definiera vårt nya kontroll flödes koncept genom att skriva en funktion som gör att Oracle kan styras och som returnerar en ny åtgärd.
På så sätt ser vi till att vår nya funktion ser ut ungefär likadant ut `Controlled` , vilket illustrerar att vi enkelt kan definiera kraftfulla nya styrnings flödes konstruktioner som använder Q# och Canon tillsammans:

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
