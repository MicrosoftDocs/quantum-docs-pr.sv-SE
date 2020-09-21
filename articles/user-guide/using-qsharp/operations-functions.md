---
title: Åtgärder och funktioner i Q#
description: Så här definierar och anropar du åtgärder och funktioner, och de kontrollerade och angränsande drifts specialiseringarna.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- Q#
- $$v
ms.openlocfilehash: c2ce999ea2a0fe7204f402fedb4cd3a3c15bd44b
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759432"
---
# <a name="operations-and-functions-in-no-locq"></a>Åtgärder och funktioner i Q#

## <a name="defining-new-operations"></a>Definiera nya åtgärder

Åtgärder är kärnan i Q# .
När de har deklarerats kan de antingen anropas från klassiska .NET-program, till exempel med hjälp av en simulator eller av andra åtgärder i Q# .
Varje åtgärd som definierats i Q# kan anropa valfritt antal andra åtgärder, inklusive de inbyggda inbyggda operationerna som definieras av språket. Det specifika sätt som Q# definierar dessa inre åtgärder beror på mål datorn.
När de kompileras visas varje åtgärd som en .NET-klass typ som kan tillhandahållas mål datorer.

Varje Q# källfil kan definiera ett valfritt antal åtgärder.
Åtgärds namn måste vara unika inom ett namn område och kan inte stå i konflikt med typ-eller funktions namn.

En åtgärds deklaration består av nyckelordet `operation` , följt av symbolen som är åtgärdens namn, en typ av identifierare som definierar argumenten för åtgärden, ett kolon `:` , en typ anteckning som beskriver åtgärdens resultat typ, eventuellt en anteckning med åtgärds egenskaper, en öppen klammerparentes och sedan texten i åtgärds deklarationen som omges av klammerparenteser `{ }` .

Varje åtgärd tar indata, genererar utdata och anger implementeringen för en eller flera åtgärds specialiseringar.
De möjliga specialiseringarna och hur du definierar och anropar dem beskrivs i de olika avsnitten i den här artikeln.
I den här övningen ska du ta hänsyn till följande åtgärd, som endast definierar en fördefinierad specialisering och använder en enda qubit som inmatad, och anropar sedan den inbyggda <xref:microsoft.quantum.intrinsic.x> åtgärden för inaktuella ingången:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Nyckelordet `operation` inleder åtgärds definitionen, följt av namnet. här, `BitFlip` .
Därefter definieras indatatypen ( `Qubit` ), tillsammans med ett namn, `target` för att referera till indatamängden i den nya åtgärden.
Till sist `Unit` definierar den här åtgärdens utdata tom.
`Unit` används på samma sätt som `void` i C# och andra tvingande språk och motsvarar `unit` i F # och andra funktionella språk.

Åtgärder kan också returnera fler intressanta typer än `Unit` .
Till exempel <xref:microsoft.quantum.intrinsic.m> returnerar åtgärden utdata av typen `Result` , vilket representerar att ha utfört ett mått.  Du kan skicka den från en åtgärd till en annan åtgärd eller använda den med `let` nyckelordet för att definiera en ny variabel.

Den här metoden gör det möjligt att representera klassisk beräkning som samverkar med Quantum-åtgärder på låg nivå, t. ex. i [upptätad kod](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding):

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> Varje åtgärd i Q# tar exakt en indata och returnerar exakt en utdata.
> Flera indata och utdata representeras med hjälp av *tupler*, som samlar in flera värden i ett enda värde.
> I detta hänseende Q# är ett "tupel-in-tupel"-språk.
> Efter det här konceptet måste en uppsättning tomma parenteser `()` läsas som "Empty"-tupel, som har typen `Unit` .

## <a name="controlled-and-adjoint-operations"></a>Kontrollerade och närliggande aktiviteter

Om en åtgärd implementerar en enhetlig omvandling, vilket är fallet för många åtgärder i Q# , är det möjligt att definiera hur åtgärden fungerar när *adjointed* eller *styrs*. En *angränsande* specialisering av en åtgärd anger hur "invertering" av åtgärden agerar, medan en *kontrollerad* specialisering anger hur en åtgärd agerar när dess program villkoras i tillståndet för en viss Quantum-registrering.

Angränsande av Quantum-åtgärder är avgörande för många aspekter av Quantum Computing. Ett exempel på en sådan situation som diskuteras tillsammans med en användbar Q# programmerings teknik finns i [Conjugations](#conjugations) i den här artikeln. 

Den kontrollerade versionen av en åtgärd är en ny åtgärd som effektivt tillämpar bas åtgärden endast om alla qubits för kontrollen är i ett visst tillstånd.
Om kontrollens qubits är i superposition tillämpas bas åtgärden på samma sätt som den aktuella delen av superpositionen.
Därmed används kontrollerade åtgärder ofta för att generera entanglement.

Naturligt, en *kontrollerad angränsande* specialisering kan också finnas, och ange det kontrollerade programmet för en åtgärd som är intilliggande.

> [!NOTE]
> Om $U $ är den enhetliga omvandling som implementeras av en åtgärd `U` , `Adjoint U` representerar den enhetliga omvandlingen $U ^ \dagger $, som är den komplexa konjugatet.
> Genom att använda en åtgärd och sedan dess angränsande status till ett tillstånd blir det oförändrat, vilket visas i det faktum att $UU ^ \dagger = U ^ \dagger U = \id $, identitets mat ris.
> Den enhetliga representationen av en kontrollerad åtgärd är något mer nyanserade, men du hittar mer information om [Quantum Computing-koncept: flera qubits](xref:microsoft.quantum.concepts.multiple-qubits).

I följande avsnitt beskrivs hur du anropar dessa olika specialiseringar i din Q# kod och hur du definierar åtgärder för att stödja dem.

### <a name="calling-operation-specializations"></a>Anropar åtgärds-specialiseringar

En *Functor* i Q# är en fabrik som definierar en ny åtgärd från en annan åtgärd.
De två standard functors i Q# är `Adjoint` och `Controlled` .

Functors har åtkomst till implementeringen av bas åtgärden när du definierar implementeringen av den nya åtgärden.
Det innebär att functors kan utföra mer komplexa funktioner än vanliga funktioner på högre nivå. Functors har ingen representation i Q# typ systemet. Det är därför inte möjligt att binda dem till en variabel eller skicka dem som argument. 

Använd en Functor genom att använda den för en åtgärd som returnerar en ny åtgärd.
Om du till exempel använder `Adjoint` Functor till `Y` åtgärden returneras den nya åtgärden `Adjoint Y` . Du kan anropa den nya åtgärden som vilken annan åtgärd som helst.
För att en åtgärd ska stödja programmet för `Adjoint` -eller `Controlled` -functors måste dess returtyp nödvändigt vis vara `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint` functor

Därför `Adjoint Y(q1)` tillämpar Functor på `Adjoint` `Y` åtgärden för att generera en ny åtgärd och tillämpar den nya åtgärden i `q1` .
Den nya åtgärden har samma signatur och typ som bas åtgärd `Y` .
I synnerhet stöder den nya åtgärden även `Adjoint` och stöder `Controlled` om och bara om bas åtgärden utfördes.
`Adjoint`Functor är en egen invertering, det vill säga är `Adjoint Adjoint Op` alltid detsamma som `Op` .

#### <a name="controlled-functor"></a>`Controlled` functor

På samma sätt `Controlled X(controls, target)` tillämpar `Controlled` Functor på `X` åtgärden för att generera en ny åtgärd och tillämpar den nya åtgärden i `controls` och `target` .

> [!NOTE]
> I Q# tar kontrollerade versioner alltid en matris med kontroll-qubits, och kontrollen är alltid baserad på alla kontroll qubits som är i beräknings `PauliZ` läge () `One` , $ \ket {1} $.
> Kontroll som bygger på andra tillstånd uppnås genom att tillämpa lämplig enhetlig drift till kontrollen qubits före den kontrollerade åtgärden, och sedan använda inversen av den enhetliga åtgärden efter den kontrollerade åtgärden.
> Om du till exempel använder en `X` åtgärd i en kontroll qubit före och efter en kontrollerad åtgärd, så gör åtgärden att kontrol lera `Zero` status ($ \ket {0} $) för den qubit, att tillämpa en `H` åtgärd före och efter kontroller i `PauliX` `One` tillstånd, d.v.s. eigenvalue för Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $ i stället för `PauliZ` `One` tillstånd.

Med ett åtgärds uttryck kan du skapa ett nytt åtgärds uttryck med hjälp av `Controlled` Functor.
Signaturen för den nya åtgärden baseras på signaturen för den ursprungliga åtgärden.
Resultat typen är densamma, men indatatypen är en två tuple med en qubit-matris som innehåller kontrollens qubit (s) som det första elementet och argumenten för den ursprungliga åtgärden som det andra elementet.
Den nya åtgärden stöder `Controlled` och stöder `Adjoint` om och endast om den ursprungliga åtgärden utfördes.

Om den ursprungliga åtgärden bara tog ett enda argument, kommer [singleton-tupel](xref:microsoft.quantum.guide.types) att spelas här.
Till exempel `Controlled X` är den kontrollerade versionen av `X` åtgärden. 
`X` har typen `(Qubit => Unit is Adj + Ctl)` , så `Controlled X` har typ `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; på grund av singleton tuple-motsvarigheten är detta samma som `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Kom ihåg att omsluta motsvarande argument för den kontrollerade versionen av åtgärden inom parentes för att konvertera dem till en tupel om bas åtgärden tog flera argument.
Till exempel `Controlled Rz` är den kontrollerade versionen av `Rz` åtgärden. 
`Rz` har typen `((Double, Qubit) => Unit is Adj + Ctl)` , så `Controlled Rz` har typen `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Därför `Controlled Rz(controls, (0.1, target))` är det ett giltigt anrop till `Controlled Rz` (Observera parenteser runt `0.1, target` ).

Ett annat exempel `CNOT(control, target)` kan implementeras som `Controlled X([control], target)` . Om ett mål ska kontrol leras av två Control qubits (CCNOT), använder du en `Controlled X([control1, control2], target)` instruktion.

#### `Controlled Adjoint` 

`Controlled`Och `Adjoint` functors återkommer, så det finns ingen skillnad mellan att tillämpa `Controlled Adjoint Op` eller `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Definiera kontrollerade och intilliggande implementeringar

I den första åtgärds deklarationen i föregående exempel, åtgärderna `BitFlip` och `DecodeSuperdense` definierades med signaturer `(Qubit => Unit)` respektive `((Qubit, Qubit) => (Result, Result))` .
Eftersom `DecodeSuperdense` omfattar mätningar är det inte en enhetlig åtgärd och därför kan ingen kontrollerad icke-angränsande specialisering finnas (återkalla det relaterade kravet att en sådan åtgärd returnerar `Unit` ).
Eftersom `BitFlip` du bara utför den enhetliga <xref:microsoft.quantum.intrinsic.x> åtgärden kan du dock ha definierat den med båda specialiseringarna.

I det här avsnittet beskrivs hur du kan ta med specialiseringar i dina Q# Åtgärds deklarationer, vilket ger dem möjlighet att anropas tillsammans med `Adjoint` eller `Controlled` functors.
För ytterligare information om några av de situationer där det är antingen giltigt eller inte giltigt för att deklarera vissa specialiseringar, se [omständigheter för giltiga definiering av specialiseringar](#circumstances-for-validly-defining-specializations) i den här artikeln.

Åtgärds egenskaper definierar vilka typer av functors som du kan tillämpa på den deklarerade åtgärden och vilken inverkan de har. Förekomsten av dessa specialiseringar kan deklareras som en del av åtgärdens signatur, särskilt genom en anteckning med drift egenskaper: `is Adj` , `is Ctl` eller `is Adj + Ctl` .
Den faktiska implementeringen av varje specialisering kan antingen *implicit* eller *uttryckligen* definieras.

### <a name="implicitly-specifying-implementations"></a>Ange implementeringar implicit

I det här fallet består bröd texten i åtgärds deklarationen enbart av standard implementeringen. Exempel:

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
Här genereras motsvarande implementering för varje sådan implicit deklarerad specialisering automatiskt av kompilatorn, som ska utföras om-eller- `Adjoint` `Controlled` functors används.

Anropet till skulle därför `Adjoint PrepareEntangledPair` leda till att kompileraren implementerar det intilliggande av `CNOT` och sedan det intilliggande `H` .
Dessa enskilda åtgärder är både egna, så att den resulterande `Adjoint PrepareEntangledPair` åtgärden bara består av att tillämpa `CNOT(here, there)` och sedan `H(here)` .
Därför kan du använda detta för att skriva `DecodeSuperdense` i föregående exempel mer komprimerings bara, genom att använda det angränsande av `PrepareEntangledPair` för att omvandla Entangled-läget tillbaka till ett unentangled-par med qubits:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Anteckningen med åtgärds egenskaperna i deklarationen är användbar för att säkerställa att kompileraren automatiskt genererar andra specialiseringar baserat på standard implementeringen. 

Det finns flera viktiga begränsningar att tänka på när du skapar åtgärder för användning med functors.
De mest kritiska och specialiseringarna för en åtgärd som använder resultatvärdet för en annan åtgärd *kan inte* genereras automatiskt av kompilatorn, eftersom det är oklart hur du ordnar om instruktionerna i en sådan åtgärd för att få samma effekt.

Därför är det ofta användbart att uttryckligen ange de olika implementeringarna.

### <a name="explicitly-specifying-implementations"></a>Ange implementeringar explicit

Om kompilatorn inte kan generera implementeringen kan du ange den explicit. Sådana uttryckliga specialiserings deklarationer kan bestå av ett lämpligt *generations direktiv* eller en användardefinierad implementering.
Följande är ett fullständigt utbud av möjligheter, med några exempel på explicit specialisering. 


#### <a name="explicit-specialization-declarations"></a>Explicita specialiserings deklarationer

Q# åtgärder kan innehålla följande uttryckliga specialiserings deklarationer:

- `body`Specialiseringen anger implementeringen av åtgärden utan att functors tillämpas.
- `adjoint`Specialiseringen anger implementeringen av åtgärden med `Adjoint` Functor tillämpad.
- `controlled`Specialiseringen anger implementeringen av åtgärden med `Controlled` Functor tillämpad.
- `controlled adjoint`Specialiseringen anger implementeringen av åtgärden med både `Adjoint` och `Controlled` functors tillämpas.
  Den här specialiseringen kan också namnges `adjoint controlled` eftersom de två functorsen går på.


En åtgärd av typen specialisering består av en specialisering (till exempel `body` eller `adjoint` ) följt av en av:

- En explicit deklaration enligt beskrivningen i följande.
- Ett *direktiv* som talar om för kompileraren *hur* du genererar specialiseringen, en av:
  - `intrinsic`, som anger att mål datorn tillhandahåller specialisering.
  - `distribute`, som används med- `controlled` och- `controlled adjoint` specialiseringarna.
    När det används med `controlled` anger det att kompilatorn ska beräkna specialiseringen genom att tillämpa `Controlled` på alla åtgärder i `body` .
    När det används med `controlled adjoint` anger det att kompilatorn ska beräkna specialiseringen genom att tillämpa `Controlled` på alla åtgärder i `adjoint` specialiseringen.
  - `invert`, som anger att kompilatorn ska beräkna `adjoint` specialiseringen genom att invertera `body` , till exempel återföra ordningen på åtgärder och tillämpa den angränsande till var och en.
    När det används med `adjoint controlled` anger detta att kompilatorn ska beräkna specialiseringen genom att invertera `controlled` specialisering.
  - `self`, för att ange att den angränsande specialiseringen är samma som `body` specialiseringen.
    Användningen `self` är giltig för- `adjoint` och- `adjoint controlled` specialiseringarna.
    För `adjoint controlled` , `self` förutsätter att `adjoint controlled` specialiseringen är samma som `controlled` specialiseringen.
  - `auto`, för att ange att kompilatorn ska välja ett lämpligt direktiv att tillämpa.
    Du kan inte använda `auto` för `body` specialisering.

Direktiven och `auto` alla kräver ett avslutande semikolon `;` .
`auto`Direktivet matchar följande genererade direktiv om en explicit deklaration av `body` tillhandahålls:

- `adjoint`Specialiseringen genereras enligt direktivet `invert` .
- `controlled`Specialiseringen genereras enligt direktivet `distribute` .
- `adjoint controlled`Specialiseringen genereras enligt direktivet `invert` om en explicit deklaration för `controlled` har givits men inte en för `adjoint` , och `distribute` annars.

> [!TIP]   
> Om en åtgärd är självständig kan du uttryckligen ange antingen den angränsande eller den kontrollerade intill-specialiseringen via generations direktivet `self` så att kompilatorn kan använda den informationen i optimerings syfte.

En specialiserings deklaration som innehåller en användardefinierad implementering består av en argument tupel följt av ett instruktions block med den Q# kod som implementerar specialiseringen.
I argument listan används för `...` att representera argumenten som har deklarerats för åtgärden som helhet.
För `body` och ska `adjoint` argument listan alltid vara `(...)` . för och måste `controlled` `adjoint controlled` argument listan vara en symbol som representerar matrisen med kontroll qubits, följt av `...` , inom parentes, till exempel `(controls,...)` .

### <a name="examples"></a>Exempel

En åtgärds deklaration kan vara så enkel som följande, som definierar den primitiva Pauli X-åtgärden:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
Observera att den angränsande av Pauli X-åtgärden definieras med direktivet `self` , eftersom efter definition `X` är en egen invertering.

I det tidigare `PrepareEntangledPair` exemplet motsvarar koden följande kod som innehåller explicita specialiserings deklarationer: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
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

#### <a name="user-defined-specialization-implementation"></a>Användardefinierad specialisering

Om kompileraren inte kan generera implementeringen för en viss specialisering automatiskt, eller om en effektivare implementering kan ges, kan du definiera implementeringen manuellt.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
I det föregående exemplet `adjoint invert;` anger att den angränsande specialiseringen ska genereras genom att invertera bröd texten och `controlled adjoint invert;` att det visar sig att den kontrollerade angränsande specialiseringen ska genereras genom att den aktuella implementeringen av den kontrollerade specialiseringen inverteras.

Om en eller flera specialiseringar förutom standard texten måste deklareras explicit måste implementeringen för standard texten omslutas till en lämplig specialiserings deklaration.

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a>Omständigheter för giltiga definiering av specialiseringar

#### <a name="operation-declarations-with-adjointcontrolled"></a>Åtgärds deklarationer med angränsande/styrda

Det är tillåtet att ange en åtgärd utan angränsande eller kontrollerade versioner. Till exempel har mått åtgärderna ingen eftersom de inte är inverteras eller kontrollerbara.

En åtgärd stöder- `Adjoint` och `Controlled` functors om dess deklaration innehåller en implicit eller explicit deklaration av respektive specialisering.

En explicit deklarerad angränsande och kontrollerad specialisering innebär att det finns en angränsande/kontrollerad specialisering. 

För en åtgärd vars brödtext innehåller upprepnings-till-lyckade-slingor, set-instruktioner, mätningar, retur-instruktioner eller anrop till andra åtgärder som inte stöder `Adjoint` Functor, genererar automatiskt en angränsande specialisering efter `invert` eller- `auto` direktivet.

För en åtgärd vars brödtext innehåller anrop till andra åtgärder som inte stöder Functor går det `Controlled` inte att skapa en kontrollerad specialisering automatiskt efter `distribute` eller- `auto` direktivet.

#### <a name="controlled-adjoint"></a>Kontrollerat från det intilliggande

Den kontrollerade, intilliggande versionen av en åtgärd anger hur du implementerar en Quantum-kontrollerad version av åtgärdens angränsande.
Det är tillåtet att ange en åtgärd utan kontrollerad version. till exempel har mått åtgärderna ingen kontrollerad, angränsande version eftersom de varken kan styras eller inverteras.

En kontrollerad, angränsande specialisering för en åtgärd måste finnas om och endast om både en intilliggande och en kontrollerad specialisering finns. I så fall härleds förekomsten av den kontrollerade angränsande specialiseringen. Om ingen implementering uttryckligen definieras genererar kompileringen en lämplig specialisering.

För en åtgärd vars brödtext innehåller anrop till andra åtgärder som inte har en kontrollerad version som inte är en kontrollerad version, så genererar automatiskt en angränsande specialisering efter `invert` , `distribute` , eller- `auto` direktivet.


### <a name="type-compatibility"></a>Skriv kompatibilitet

Använd en åtgärd med ytterligare functors som stöds överallt där du använder en åtgärd med färre functors men samma signatur. Använd till exempel en åtgärd av typen `(Qubit => Unit is Adj)` överallt där du använder en åtgärd av typen `(Qubit => Unit)` .

Q# är *samvariant* med avseende på anrops bara Retur typer: ett anrop som returnerar en typ `'A` är kompatibelt med ett anrop med samma Indatatyp och en resultat typ som är kompatibel med `'A` .

Q# är *contravariant* med avseende på indatatyper: ett anrop som använder en typ `'A` som indatamängd är kompatibelt med ett anrop med samma resultat typ och en indatatyp som är kompatibel med `'A` .

Det innebär att man får följande definitioner,

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

Du kan

- Anropa funktionen `ConjugateInvertWith` med ett `inner` argument för antingen `Invert` eller `ApplyUnitary` .
- Anropa funktionen `ConjugateUnitaryWith` med ett `inner` argument av `ApplyUnitary` , men inte `Invert` .
- Returnera ett värde av typen `(Qubit[] => Unit is Adj + Ctl)` från `ConjugateInvertWith` .

> [!IMPORTANT]
> Q# 0,3 introducerade en betydande skillnad i beteendet för användardefinierade typer.

Användardefinierade typer behandlas som en omsluten version av den underliggande typen, i stället för som en undertyp.
Det innebär att det inte går att använda ett värde av en användardefinierad typ där du förväntar dig ett värde av den underliggande typen.


### <a name="conjugations"></a>Conjugations

Till skillnad från klassiska bitar är det något mer engagerande att frigöra Quantum-minne eftersom qubits kan ha oönskade effekter på den återstående beräkningen om qubits fortfarande är Entangled. Dessa effekter kan undvikas genom att du avregistrerar utförda beräkningar innan du frigör minnet. Ett vanligt mönster i Quantum Computing är därför följande: 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

Från och med vår 0,9-version Q# har stöd för en conjugation-instruktion som implementerar föregående omvandling. Med den här instruktionen `ApplyWith` kan åtgärden implementeras på följande sätt:

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
En sådan conjugation-instruktion är mycket mer användbar om de yttre och inre omvandlingarna inte är tillgängliga som åtgärder utan är i stället bekväma att beskriva genom ett block som består av flera instruktioner. 

Den inverterade omvandlingen för de instruktioner som definierats inom blocket genereras automatiskt av kompileraren och körs när Apply-blocket har slutförts.
Eftersom alla föränderligt-variabler som används som en del av inom-blocket inte kan bindas om i Apply-blocket, garanteras den genererade omvandlingen som det angränsande av beräkningen i avsnittet-block. 


## <a name="defining-new-functions"></a>Definiera nya funktioner

Functions är helt deterministiska, klassiska rutiner i Q# , som är distinkta från åtgärder i så att de inte får ha några effekter utöver att beräkna ett utdata-värde.
I synnerhet kan funktioner inte anropa åtgärder. agera på, allokera eller låna qubits; exempel på slumpmässiga siffror; eller på annat sätt är beroende av ett tillstånd bortom indatavärdet till en funktion.
Som en följd Q# är funktioner *rena*, där de alltid mappar samma indatavärden till samma utdata-värden.
Det här beteendet gör det möjligt Q# för kompileraren att på ett säkert sätt ändra ordning på hur och när du ska anropa funktioner när du genererar specialisering

Varje Q# källfil kan definiera valfritt antal funktioner.
Funktions namn måste vara unika inom ett namn område och får inte stå i konflikt med åtgärds-eller typnamn.

Att definiera en funktion fungerar på samma sätt för att definiera en åtgärd, förutom att inga angränsande eller kontrollerade specialiseringar kan definieras för en funktion.
Till exempel:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

eller 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a>Klassisk logik i functions = = Hej

När det är möjligt är det bra att skriva ut klassisk logik i termer av funktioner i stället för åtgärder så att åtgärder kan användas mer. Om du till exempel hade skrivit den tidigare `Square` deklarationen som en *åtgärd*skulle kompileraren inte ha kunnat garantera att anropet till den med samma indata skulle skapa samma utdata konsekvent.

Om du vill ta del av skillnaden mellan Functions och åtgärder kan du tänka på problemet med att slumpmässigt sampla ett slumpmässigt nummer i en Q# åtgärd:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Varje tid som `U` anropas har det en annan åtgärd på `target` .
I synnerhet kan kompileraren inte garantera att om du lägger till en `adjoint auto` specialisering-deklaration i `U` fungerar den `U(target); Adjoint U(target);` som identitet (det vill säga som en no-OP).
Detta bryter mot definitionen av det intilliggande som definierats i [vektorer och matriser](xref:microsoft.quantum.concepts.vectors), så att kompileraren automatiskt genererar en angränsande specialisering i en åtgärd där du anropar åtgärden <xref:microsoft.quantum.math.randomreal> skulle bryta de garantier som tillhandahålls av kompilatorn, <xref:microsoft.quantum.math.randomreal> är en åtgärd för vilken det inte finns något angränsande eller styrd version.

Å andra sidan tillåter funktions anrop som `Square` är säkra, och är säkra på att kompileraren att den bara behöver bevara indatan för `Square` att hålla dess utdata stabil.
Att isolera så mycket klassisk logik som möjligt i functions gör det lätt att återanvända den logiken i andra funktioner och åtgärder.


## <a name="generic-type-parameterized-callables"></a>Generisk (typ Parameterad) Callables

Många funktioner och åtgärder som du kanske vill definiera är inte tungt förlitade på typerna av deras indata, utan används i stället för att implicit använda sina typer via en annan funktion eller åtgärd.
Anta till exempel att *mappnings* konceptet är gemensamt för många funktionella språk; med en Function $f (x) $ och en samling värden $ \{ x_1, x_2, \dots, x_n \} $, returnerar kartan en ny samling $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.
För att implementera detta i Q# , dra nytta av det faktum att funktionerna är första klass.
Här är ett snabbt exempel på `Map` , `T` som använder som plats hållare när du tar reda på vilka typer du behöver.

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Observera att den här funktionen ser mycket likadan ut oavsett vilka faktiska typer som du ersätter i.
En karta från heltal till Paulis, till exempel, ser ut ungefär likadant som en karta från flytt ALS nummer till strängar:

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

I princip kan du skriva en version av `Map` för varje par av typer som du stöter på, men det ger upphov till flera problem.
Om du till exempel hittar ett fel i `Map` måste du se till att korrigeringen tillämpas enhetligt i alla versioner av `Map` .
Om du skapar en ny tupel eller UDT måste du dessutom också skapa en ny `Map` för att gå vidare med den nya typen.
Även om det här är ett litet antal sådana funktioner kan det vara orimligt att införa fler och fler funktioner i samma formulär som `Map` , men kostnaden för att introducera nya typer blir orimligt stor i relativt kort ordning.

Det är dock mycket av detta problem att du inte har gett kompilatorn den information som krävs för att identifiera hur de olika versionerna av `Map` är relaterade.
I praktiken vill du att kompileraren ska behandla `Map` som en typ av matematisk funktion från Q# *typer* till Q# functions.

Q# formalizes det här begreppet genom att tillåta att funktioner och åtgärder har *typ parametrar*, samt de vanliga tuple-parametrarna.
I föregående exempel vill du tänka på att `Map` ha typ parametrar `Int, Pauli` i det första fallet och `Double, String` i det andra fallet.
För det mesta använder du de här typ parametrarna som om de var vanliga typer. Använd värden av typen parametrar för att skapa matriser och tupler, anropa funktioner och åtgärder och tilldela till vanliga variabler eller föränderligt.

> [!NOTE]
> Det mest extrema fallet med indirekt beroende är att qubits, där ett Q# program inte kan förlita sig på typen av struktur, `Qubit` men **måste** skicka sådana typer till andra funktioner och funktioner.

När du återvänder till det tidigare exemplet ser du att `Map` måste ha typ parametrar, en för att representera indata till `fn` och en för att representera utdata från `fn` .
I Q# skrivs detta genom att lägga till vinkelparenteser (det vill säga `<>` inte bromsar $ \braket {} $!) efter namnet på en funktion eller åtgärd i dess deklaration, och genom att ange varje typ parameter.
Namnet på varje typ parameter måste börja med en Ticket `'` , vilket indikerar att det är en typ parameter och inte en vanlig typ (kallas även *konkret* typ).
Därför `Map` skrivs:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Observera att definitionen av `Map<'Input, 'Output>` ser ut så mycket som previoius-versionerna.
Den enda skillnaden är att du uttryckligen har informerat kompilatorn som `Map` inte är direkt beroende av vad `'Input` och `'Output` är, men fungerar för två typer genom att använda dem indirekt genom `fn` .
När du har definierat `Map<'Input, 'Output>` på det här sättet kan du anropa det som om det var en vanlig funktion:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Att skriva allmänna funktioner och åtgärder är en plats där "tuple-in-tupel" är ett mycket användbart sätt att tänka på Q# funktioner och åtgärder.
> Eftersom varje funktion tar exakt en indata och returnerar exakt en utmatning, matchar en indata typen `'T -> 'U` *all* Q# funktion.
> På samma sätt kan du skicka alla åtgärder till en indatatyp `'T => 'U` .

Som ett andra exempel bör du tänka på utmaningen med att skriva en funktion som returnerar kompositionen av två andra funktioner:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Här måste du ange exakt vad `A` , `B` och `C` är, och därmed begränsa verktyget för vår nya `Compose` funktion.
Efter alla är det `Compose` bara beroende av `A` , `B` , och `C` *via* `innerFn` och `outerFn` .
Alternativt kan du lägga till typ parametrar som `Compose` anger att det fungerar för *alla* `A` , `B` och `C` , så länge parametrarna matchar de som förväntas av `innerFn` och `outerFn` :

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Q#Standard biblioteken tillhandahåller en rad olika typer av parameter åtgärder och funktioner som gör det enklare att uttrycka kontroll flödet.
Dessa beskrivs ytterligare i [ Q# standard biblioteks guiden](xref:microsoft.quantum.libraries.standard.intro).


## <a name="callables-as-first-class-values"></a>Callables som värden i den första klassen

En viktig teknik för att motivera att kontrol lera flöde och klassisk logik med hjälp av funktioner i stället för åtgärder är att använda samma åtgärder och funktioner i som Q# *första klass*.
Det innebär att de är varje värde på språket i sin egen rätt.
Till exempel är följande en perfekt giltig Q# kod, om en liten indirekta:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

Värdet för variabeln `ourH` i föregående kodfragment är sedan åtgärden <xref:microsoft.quantum.intrinsic.h> , så att du kan anropa det värdet som vilken annan åtgärd som helst.
Med den här möjligheten kan du skriva åtgärder som utför åtgärder som en del av deras indata, vilket utgör koncept för kontroll flöde med högre ordning.
Du kan till exempel föreställa oss en åtgärd genom att använda den två gånger till samma mål-qubit.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Returnera åtgärder från en funktion

Det är viktigt att betona att du även kan returnera åtgärder som en del av utdata, så att du kan isolera vissa typer av klassisk villkorlig logik som en klassisk funktion som returnerar en beskrivning av ett Quantum-program i form av en åtgärd.
Ett enkelt exempel är att ta med i exemplet på Teleportion, i vilken parten som tar emot ett tvåsidigt meddelande med två bitar måste använda meddelandet för att avkoda sin qubit till rätt transport tillstånd.
Du kan skriva detta i termer av en funktion som tar de två klassiska bitarna och returnerar rätt avkodnings åtgärd.

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

Den här nya funktionen är en funktion, i den här om du anropar den med samma värden `hereBit` och `thereBit` , så kommer du alltid tillbaka till samma åtgärd.
Därför kan avkodaren på ett säkert sätt köras i åtgärder utan att behöva känna till hur avkodnings logiken interagerar med definitionerna för de olika specialiseringarna för åtgärder.
Det vill säga att den klassiska logiken i en funktion är isolerad, vilket garanterar att-kompilatorn som funktions anropet kan ordnas om med impunity, så länge som indatamängden bevaras.


## <a name="partial-application"></a>Partiellt program

Du kan göra mycket mer med funktioner som returnerar åtgärder med hjälp av *partiella program*, där du anger en eller flera delar av indatamängden för en funktion eller åtgärd utan att faktiskt anropa den. I det tidigare `ApplyTwice` exemplet kan du ange att du inte vill ange, till och med vilken qubit den inmatade åtgärden ska gälla:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

I det här fallet innehåller den lokala variabeln `twiceOp` den delvis tillämpade åtgärden `ApplyTwice(op, _)` , där `_` anger delar av de inmatade värden som ännu inte har angetts.
När du anropar `twiceOp` Nästa rad skickar du som intill den delvis tillämpade åtgärden alla återstående delar av indatamängden till den ursprungliga åtgärden.
Därför är det tidigare kodfragmentet identiskt med att anropa `ApplyTwice(op, target)` direkt, Spara för att du har infört en ny lokal variabel så att du kan försena anropet samtidigt som du tillhandahåller vissa delar av indatan.

Eftersom en åtgärd som har tillämpats delvis inte anropas förrän hela indata har angetts, kan du på ett säkert sätt tillämpa åtgärder även inifrån functions.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

I princip skulle den klassiska logiken i `SquareOperation` ha varit mycket mer engagerad, men den är fortfarande isolerad från resten av en åtgärd av de garantier som kompileraren kan erbjuda om functions. Q#Standard biblioteket använder den här metoden i hela för att uttrycka klassiskt kontroll flöde på ett sätt som kan användas av Quantum-program.


## <a name="recursion"></a>Rekursion

Q# callables kan vara direkt eller indirekt rekursivt.
Det vill säga en åtgärd eller funktion kan anropa sig själv, eller så kan den anropa ett annat anrop som direkt eller indirekt anropar den anropande åtgärden.

Det finns två viktiga kommentarer om användningen av rekursion, men:

- Användningen av rekursion i åtgärder är sannolikt att störa vissa optimeringar.
  Den här störningen kan ha en betydande inverkan på körnings tiden för algoritmen.
- När det körs på en faktisk Quantum-enhet kan stack utrymmet vara begränsat och så att djup rekursion kan leda till ett körnings fel.
  I synnerhet Q# identifierar kompileraren och körnings miljön inte och optimerar slut för and rekursion.

## <a name="next-steps"></a>Nästa steg

Lär dig mer om [variabler](xref:microsoft.quantum.guide.variables) i Q# .