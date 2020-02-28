---
title: 'Q #-åtgärder och-funktioner'
description: 'Läs mer om åtgärder och funktioner i Q # och hur de används i ett Quantum-program.'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 43f0cf2da192a607e514d0c7de57a9bdd067faf7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907672"
---
# <a name="q-operations-and-functions"></a>Q #-åtgärder och-funktioner

Q #-program består av en eller flera *åtgärder* som beskriver sido effekter i Quantum-åtgärder kan ha på Quantum data och en eller flera *funktioner* som tillåter ändringar i klassiska data. Till skillnad från åtgärder används funktioner för att beskriva rent klassiskt beteende och har inga effekter, förutom att använda klassiska utmatnings värden.

Varje åtgärd som definierats i Q # kan sedan anropa valfritt antal andra åtgärder, inklusive inbyggda, inbyggda åtgärder som definierats av språket. Det specifika sätt på vilket dessa inbyggda åtgärder definieras beror på mål datorn. När de kompileras visas varje åtgärd som en .NET-klass typ som kan tillhandahållas mål datorer.

## <a name="defining-new-operations"></a>Definiera nya åtgärder

Som beskrivs ovan är det mest grundläggande Bygg blocket av ett Quantum-program som skrivits i Q # en *åtgärd*som antingen kan anropas från klassiska .NET-program, t. ex., med hjälp av en simulator eller andra åtgärder inom Q #.
Varje åtgärd tar indata, genererar utdata och anger implementeringen för en eller flera åtgärds specialiseringar.
Följande åtgärd definierar t. ex. endast en fördefinierad specialisering och använder en enda qubit som inmatad, och anropar sedan den inbyggda `X` åtgärden på ingången:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Nyckelordet `operation` startar åtgärds definitionen och följs av namnet. här `BitFlip`.
Därefter definieras indatatypen som `Qubit`, tillsammans med ett namn `target` för att referera till indatamängden i den nya åtgärden.
På samma sätt definierar `Unit` att åtgärdens utdata är tom.
Detta används på samma sätt som `void` i C# och andra tvingande språk, och motsvarar `unit` i F# och andra funktionella språk.

> [!NOTE]
> Vi kommer att utforska detta i mer detalj nedan, men varje åtgärd i Q # tar exakt en indata och returnerar exakt en utmatning.
> Flera indata och utdata visas sedan med hjälp av *tupler*, som samlar in flera värden i ett enda värde.
> Vi säger att Q # är ett "tupel-in-tupel"-språk.
> Efter det här konceptet bör `()` läsas som "Empty"-tupel, som har typen `Unit`.

I den nya åtgärden kan implementeringen anges direkt i deklarationen om endast implementeringen av standard-specialisering måste anges explicit. Dessutom är det möjligt att definiera implementeringar av, till exempel en eller flera `functor` åtgärder, enligt nedan. I exemplet ovan är den enda instruktionen att anropa den inbyggda Q #-åtgärden <xref:microsoft.quantum.intrinsic.x>.

Åtgärder kan också returnera fler intressanta typer än `Unit`.
Till exempel returnerar <xref:microsoft.quantum.intrinsic.m>-åtgärden utdata av typen `Result`som representerar att ha utfört ett mått. Vi kan antingen skicka utdata från en åtgärd till en annan åtgärd eller använda det med nyckelordet `let` för att definiera en ny variabel.
<!-- Link to UID for superdense conceptual and example documentation. -->
Detta gör det möjligt att representera klassisk beräkning som samverkar med Quantum-åtgärder på låg nivå, till exempel i upptätad kod:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a>Functors, angränsande och styrd
Om en åtgärd implementerar en enhetlig omvandling, är det möjligt att definiera hur åtgärden fungerar när *adjointed* eller *kontrol leras*. En angränsande specialisering av en åtgärd anger hur den fungerar när den körs i omvänd ordning, medan en kontrollerad specialisering anger hur en åtgärd fungerar när den tillämpas på tillståndet för ett Quantum-register.
Förekomsten av dessa specialiseringar kan deklareras som en del av åtgärdens signatur: `is Adj + Ctl` i följande exempel. Motsvarande implementering för varje sådan implicit deklarerad specialisering genereras sedan av kompileraren. 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> Många åtgärder i Q # representerar våra portar.
> Om $U $ är den enhetliga porten som representeras av en åtgärd `U``Adjoint U` representerar den enhetliga porten $U ^ \dagger $.

Om implementeringen inte kan genereras av kompilatorn kan den uttryckligen anges. Sådana uttryckliga specialiserings deklarationer kan bestå av ett lämpligt generations direktiv eller en användardefinierad implementering. Koden i `PrepareEntangledPair` ovan motsvarar exempelvis koden nedan som innehåller explicita specialiserings deklarationer: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
Nyckelordet `auto` anger att kompilatorn ska fastställa hur specialiserings implementeringen ska genereras.
Om kompileraren inte kan generera implementeringen för en viss specialisering automatiskt, eller om en effektivare implementering kan ges, kan implementeringen också definieras manuellt.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
I exemplet ovan anger `adjoint invert;` att den angränsande specialiseringen ska genereras genom att invertera bröd texten och `controlled adjoint invert;` anger att den kontrollerade intilliggande specialiseringen ska genereras genom att den angivna implementeringen av den kontrollerade specialiseringen inverteras.

Vi kommer att se fler exempel på detta i [kontroll flödet med högre ordning](xref:microsoft.quantum.concepts.control-flow).

Om du vill anropa en specialisering av en åtgärd använder du `Adjoint` eller `Controlled` nyckelord.
Exemplet över upptätt kodning ovan kan skrivas mer komprimerat genom att använda det angränsande `PrepareEntangledPair` för att transformera Entangled-läget till ett unentangled-par med qubits:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Det finns ett antal viktiga begränsningar som du bör tänka på när du skapar åtgärder för användning med functors.
De mest kritiska och specialiseringarna för en åtgärd som använder resultatvärdet för en annan åtgärd kan inte genereras automatiskt av kompilatorn, eftersom det är oklart hur du ordnar om instruktionerna i en sådan åtgärd för att få samma effekt.


## <a name="defining-new-functions"></a>Definiera nya funktioner

Med hjälp av Q # kan du också definiera *funktioner*som skiljer sig från åtgärder på så sätt att de inte får ha några effekter utöver att beräkna ett utdata-värde.
I synnerhet kan funktioner inte anropa åtgärder, agera på qubits, sampla slumpmässiga tal eller på annat sätt vara beroende av ett tillstånd bortom indatavärdet till en funktion.
Som en följd är Q #-funktioner *rena*, där de alltid mappar samma indatavärden till samma utdata-värden.
På så sätt kan Q #-kompilatorn ändra ordning på hur och när-funktioner anropas när de genererar drifts specialiseringar.

Att definiera en funktion fungerar på samma sätt för att definiera en åtgärd, förutom att inga angränsande eller kontrollerade specialiseringar kan definieras för en funktion.
Exempel:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
När det är möjligt är det bra att skriva ut klassisk logik i termer av funktioner i stället för åtgärder, så att den kan användas mer i drift.
Om vi har skrivit `Square` som en åtgärd, t. ex., skulle kompilatorn inte ha kunnat garantera att anropet till samma indata konsekvent resulterar i samma utdata.

Om du vill ta del av skillnaden mellan funktioner och åtgärder bör du tänka på problemet med att slumpmässigt sampla ett slumpmässigt tal från en Q #-åtgärd:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Varje `U` anropas, kommer den att ha en annan åtgärd på `target`.
I synnerhet kan kompileraren inte garantera att om vi har lagt till en `adjoint auto` specialisering-deklaration i `U`, så `U(target); Adjoint U(target);` fungerar som identitet (dvs. som No-OP).
Detta strider mot definitionen av det angränsande som vi såg i [vektorer och matriser](xref:microsoft.quantum.concepts.vectors), till exempel för att automatiskt generera en angränsande specialisering i en åtgärd där vi har anropat åtgärden <xref:microsoft.quantum.math.randomreal> skulle bryta mot de garantier som kompileraren tillhandahåller. <xref:microsoft.quantum.math.randomreal> är en åtgärd för vilken det inte finns något angränsande eller styrd version.

Å andra sidan är det möjligt att tillåta funktions anrop som `Square` är säkra, eftersom kompileraren kan vara säker på att den bara behöver bevara indata till `Square` för att hålla dess utdata stabil.
Att isolera så mycket klassisk logik som möjligt i functions gör det lätt att återanvända den logiken i andra funktioner och åtgärder.

## <a name="control-flow"></a>Kontrollflöde

I en åtgärd eller funktion körs varje instruktion i ordning, på liknande sätt som de flesta vanliga tvingande klassiska språk.
Det här kontroll flödet kan ändras, men på tre olika sätt:

- `if`-instruktioner
- `for` slingor
- `repeat`-`until`-slingor

Vi kommer att skjuta upp diskussionen av den senare tills vi diskuterar [ru: er-](xref:microsoft.quantum.techniques.qubits#measurements) kretsar.
`if` och `for` kontroll flödes konstruktioner går det dock bra att känna till de flesta klassiska programmeringsspråk.
I synnerhet kan ett `if`-uttryck ta ett villkor, kan följas av en eller flera `elif`-instruktioner och kan avslutas med en `else`:

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

På samma sätt visar `for`-slingor iteration över ett heltals intervall eller över elementen i en matris:

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

Det är viktigt att `for`-slingor och `if`-uttryck även kan användas i åtgärder för vilka specialisering genereras automatiskt. I så fall vänder sig den angränsande av en `for`-slinga riktningen och tar det angränsande av varje iteration.
Det här följer principen "skor-och-SOCKS": om du vill ångra att du kommer igång på SOCKS och sedan skor måste du ångra att sätta på skor och sedan ångra att sätta igång på SOCKS.
Det fungerar mindre bra om du vill prova och ta din SOCKS medan du fortfarande använder dina skor!

## <a name="operations-and-functions-as-first-class-values"></a>Åtgärder och funktioner som värden i den första klassen

En viktig teknik för uppföljning av kontroll flöde och klassisk logik med hjälp av funktioner i stället för åtgärder är att använda dessa åtgärder och funktioner i Q # är *första-klass*.
Det innebär att de är varje värde på språket i sin egen rätt.
Följande är till exempel en perfekt giltig Q #-kod, om en liten indirekta:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

Värdet för variabeln `ourH` i kodfragmentet ovan är sedan åtgärden <xref:microsoft.quantum.intrinsic.h>, så att vi kan anropa det värdet som vilken annan åtgärd som helst.
På så sätt kan vi skriva åtgärder som utför åtgärder som en del av deras indata, vilket utgör en högre ordning för kontroll flödes koncept.
Vi kan till exempel föreställa oss en åtgärd genom att använda den två gånger för samma mål-qubit.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

I det här exemplet `=>` pilen som visas i typen `(Qubit => Unit)` anger att inmatnings fältet `op` är en åtgärd som tar indata av typen `Qubit` och skapar en tom tupel som utdata.
Dessutom anger vi egenskaperna för den åtgärds typen som innehåller den information om vilka functors som stöds.
En åtgärd av typen `(Qubit => Unit)` stöder varken `Adjoint` eller `Controlled` Functor. Om vi vill ange att en åtgärd av den typen måste ha stöd för t. ex. `Adjoint` Functor måste vi deklarera den som adjointable. Detta görs med hjälp av antecknings `is Adj` till typen. På samma sätt anger `(Qubit => Unit is Ctl)` att en åtgärd av den typen stöder `Controlled`-Functor. Vi kommer att utforska detta ytterligare när vi diskuterar [typer i Q #](xref:microsoft.quantum.language.type-model) i allmänhet.

För närvarande betonar vi att vi även kan returnera åtgärder som en del av utdata, så att vi kan isolera vissa typer av klassisk villkorlig logik som en klassisk funktion som returnerar en beskrivning av ett Quantum-program i form av en åtgärd.
Ett enkelt exempel är att ta med i exemplet på Teleportion, i vilken parten som tar emot ett tvåsidigt meddelande med två bitar måste använda meddelandet för att avkoda sin qubit till rätt transport tillstånd.
Vi kan skriva detta i termer av en funktion som tar de två klassiska bitarna och returnerar rätt avkodnings åtgärd.

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

Den här nya funktionen är en funktion, där om vi anropar den med samma värden som `hereBit` och `thereBit`, kommer vi alltid att få tillbaka samma åtgärd.
Därför kan avkodaren köras inuti åtgärder utan att du behöver tänka på hur avkodnings logiken interagerar med definitionerna för de olika specialiseringarna för åtgärder.
Det vill säga att vi har isolerat den klassiska logiken i en funktion, vilket garanterar att den kompilerare som funktions anropet kan ordnas om med impunity, så länge som indatamängden bevaras.

Vi kan också behandla funktioner som värden i den första klassen, eftersom vi kommer att se mer information när vi diskuterar [drift-och funktions typer](#operations-and-functions-as-first-class-values).

## <a name="partially-applying-operations-and-functions"></a>Delvis tillämpade åtgärder och funktioner

Vi kan göra mycket mer med funktioner som returnerar åtgärder med hjälp av *partiella program*, där vi kan tillhandahålla en eller flera delar av indatamängden för en funktion eller åtgärd utan att faktiskt anropa det. Om du till exempel återkallar `ApplyTwice` exemplet ovan kan vi indikera att vi inte vill ange, till och med vilken qubit den inmatade åtgärden ska gälla:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

I det här fallet har den lokala variabeln `twiceOp` den delvis tillämpade åtgärden `ApplyTwice(op, _)`, där delar av de inmatade värden som ännu inte har angetts anges av `_`.
När vi faktiskt kallar `twiceOp` på nästa rad, skickar vi som intill den delvis tillämpade åtgärden alla återstående delar av indatamängden till den ursprungliga åtgärden.
Därför är ovanstående kodfragment detsamma som att ha anropat `ApplyTwice(op, target)` direkt, och spara för att vi har introducerat en ny lokal variabel som gör det möjligt för oss att försena samtalet samtidigt som du tillhandahåller vissa delar av indatan.

Eftersom en åtgärd som har tillämpats delvis inte anropas förrän hela indatan har tillhandahållits, kan vi på ett säkert sätt tillämpa åtgärder även inifrån functions.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

I princip skulle den klassiska logiken i `SquareOperation` ha varit mycket mer involverad, men den är fortfarande isolerad från resten av en åtgärd av de garantier som kompileraren kan erbjuda om functions.
Den här metoden kommer att användas i ett standard bibliotek i Q # för att uttrycka klassiskt kontroll flöde på ett sätt som kan användas i Quantum-program.
