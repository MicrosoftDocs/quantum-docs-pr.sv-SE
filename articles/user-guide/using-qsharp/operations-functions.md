---
title: 'Åtgärder och funktioner i Q #'
description: Så här definierar och anropar du åtgärder och funktioner, och de kontrollerade och angränsande drifts specialiseringarna.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 6cfc1b14d86e86a1cbf0109d5e81dfe50c3a80bf
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630221"
---
# <a name="operations-and-functions-in-q"></a>Åtgärder och funktioner i Q #

## <a name="defining-new-operations"></a>Definiera nya åtgärder

Åtgärder är kärnan i Q #.
När de har deklarerats kan de antingen anropas från klassiska .NET-program, t. ex. genom att använda en simulator eller andra åtgärder inom Q #.
Varje åtgärd som definierats i Q # kan sedan anropa valfritt antal andra åtgärder, inklusive inbyggda, inbyggda åtgärder som definierats av språket. Det specifika sätt på vilket dessa inbyggda åtgärder definieras beror på mål datorn.
När de kompileras visas varje åtgärd som en .NET-klass typ som kan tillhandahållas mål datorer.

Varje Q #-källfil kan definiera valfritt antal åtgärder.
Åtgärds namn måste vara unika inom ett namn område och får inte stå i konflikt med typ-eller funktions namn.

En åtgärds deklaration består av nyckelordet `operation` följt av symbolen som är åtgärdens namn, en typ av identifierare som definierar argumenten för åtgärden, ett kolon `:` , en typ anteckning som beskriver åtgärdens resultat typ, eventuellt en anteckning med åtgärds egenskaper, en öppen klammer `{` , bröd texten i åtgärds deklarationen och en avslutande klammerparentes `}` .

Varje åtgärd tar indata, genererar utdata och anger implementeringen för en eller flera åtgärds specialiseringar.
De möjliga specialiseringarna och hur du definierar/anropar dem beskrivs nedan.
I den här övningen ska du ta hänsyn till följande åtgärd, som endast definierar en fördefinierad specialisering och använder en enda qubit som inmatad, och anropar sedan den inbyggda <xref:microsoft.quantum.intrinsic.x> åtgärden för inaktuella ingången:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Nyckelordet `operation` inleder åtgärds definitionen och följs av namnet. här, `BitFlip` .
Därefter definieras indatatypen som `Qubit` , tillsammans med ett namn som `target` refererar till indatamängden i den nya åtgärden.
På samma sätt `Unit` definierar den att åtgärdens utdata är tom.
Detta används på samma sätt som `void` i C# och andra tvingande språk och motsvarar `unit` i F # och andra funktionella språk.

Åtgärder kan också returnera fler intressanta typer än `Unit` .
Till exempel <xref:microsoft.quantum.intrinsic.m> returnerar åtgärden utdata av typen `Result` , vilket representerar att ha utfört ett mått. Vi kan antingen skicka utdata från en åtgärd till en annan åtgärd eller använda det med `let` nyckelordet för att definiera en ny variabel.

Detta gör det möjligt att representera klassisk beräkning som samverkar med Quantum-åtgärder på låg nivå, till exempel i [upptätad kod](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):

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
> Varje åtgärd i Q # tar exakt en indata och returnerar exakt en utmatning.
> Flera indata och utdata visas sedan med hjälp av *tupler*, som samlar in flera värden i ett enda värde.
> Vi säger att Q # är ett "tupel-in-tupel"-språk.
> Följande begrepp `()` bör sedan läsas som "Empty"-tupel, som har typen `Unit` .


## <a name="controlled-and-adjoint-operations"></a>Kontrollerade och närliggande aktiviteter

Om en åtgärd implementerar en enhetlig omvandling, vilket är fallet för många åtgärder i Q #, är det möjligt att definiera hur åtgärden fungerar när *adjointed* eller *styrs*. En *angränsande* specialisering av en åtgärd anger hur "invertering" av åtgärden agerar, medan en *kontrollerad* specialisering anger hur en åtgärd agerar när dess program villkoras i tillståndet för en viss Quantum-registrering.

Angränsande av Quantum-åtgärder är avgörande för många aspekter av Quantum Computing. I avsnittet [Conjugations](#conjugations) kan du se en sådan situation som diskuteras tillsammans med en användbar Q # programmerings teknik.

Den kontrollerade versionen av en åtgärd är en ny åtgärd som effektivt tillämpar bas åtgärden endast om alla qubits för kontrollen är i ett visst tillstånd.
Om kontrollens qubits är i superposition tillämpas bas åtgärden på samma sätt som den aktuella delen av superpositionen.
Därmed används kontrollerade åtgärder ofta för att generera entanglement.

Naturligt, en *kontrollerad angränsande* specialisering kan också finnas, och ange det kontrollerade programmet för en åtgärd som är intilliggande.

> [!NOTE]
> Om $U $ är den enhetliga omvandling som implementeras av en åtgärd `U` , `Adjoint U` representerar den enhetliga omvandlingen $U ^ \dagger $, som är den komplexa konjugatet.
> Genom att använda en åtgärd och sedan dess angränsande status till ett tillstånd blir det oförändrat, vilket visas i det faktum att $UU ^ \dagger = U ^ \dagger U = \id $, identitets mat ris.
> Den enhetliga representationen av en kontrollerad åtgärd är något mer nyanserade, men du hittar mer information om [Quantum Computing-koncept: flera qubits](xref:microsoft.quantum.concepts.multiple-qubits).

I följande avsnitt beskrivs hur du anropar dessa olika specialiseringar i din Q #-kod.
Nedan förklarar vi hur du definierar åtgärder för att stödja dem.

### <a name="calling-operation-specializations"></a>Anropar åtgärds-specialiseringar

En *Functor* i Q # är en fabrik som definierar en ny åtgärd från en annan åtgärd.
De två standard functors i Q # är `Adjoint` och `Controlled` .

Functors har åtkomst till implementeringen av bas åtgärden när du definierar implementeringen av den nya åtgärden.
Det innebär att functors kan utföra mer komplexa funktioner än vanliga funktioner på högre nivå. Functors har ingen representation i Q #-typ systemet. Det är därför inte möjligt att binda dem till en variabel eller skicka dem som argument. 

En Functor används genom att tillämpa den på en åtgärd och returnera en ny åtgärd.
Till exempel skrivs åtgärden som resulterar i `Adjoint` att tillämpa Functor på `Y` åtgärden som `Adjoint Y` .
Den nya åtgärden kan sedan anropas som vilken annan åtgärd som helst.
För att en åtgärd ska kunna stödja program av `Adjoint` och/eller `Controlled` functors måste dess returtyp nödvändigt vis vara `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint`functor

Därmed `Adjoint Y(q1)` använder det intilliggande Functor för `Y` åtgärden för att generera en ny åtgärd och tillämpar den nya åtgärden i `q1` .
Den nya åtgärden har samma signatur och typ som bas åtgärd `Y` .
I synnerhet tillåter den nya åtgärden också `Adjoint` , och kommer att tillåta `Controlled` om och bara om bas åtgärden utfördes.
Det intilliggande Functor är en egen invertering; det vill säga är `Adjoint Adjoint Op` alltid detsamma som `Op` .

#### <a name="controlled-functor"></a>`Controlled`functor

På samma sätt `Controlled X(controls, target)` tillämpar den kontrollerade Functor på `X` åtgärden för att generera en ny åtgärd och tillämpar den nya åtgärden i `controls` och `target` .

> [!NOTE]
> I Q # tar kontrollerade versioner alltid en matris med Control-qubits och det angivna läget är alltid för alla kontroll qubits att vara i beräknings `PauliZ` läge () `One` , $ \ket {1} $.
> Kontroll som bygger på andra tillstånd kan uppnås genom att tillämpa lämplig enhetlig drift till kontrollen qubits före den kontrollerade åtgärden, och sedan använda inversen av den enhetliga åtgärden efter den kontrollerade åtgärden.
> Om du till exempel använder en `X` åtgärd i en kontroll qubit före och efter en kontrollerad åtgärd, kommer åtgärden att kontrol lera `Zero` status ($ \ket {0} $) för den qubit. att tillämpa en `H` åtgärd innan och efter kommer att ha kontroll över `PauliX` `One` statusen, d.v.s. eigenvalue för Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $ i stället för `PauliZ` `One` tillstånd.

Ett nytt åtgärds uttryck kan skapas med hjälp av Functor för ett åtgärds uttryck `Controlled` .
Signaturen för den nya åtgärden baseras på signaturen för den ursprungliga åtgärden.
Resultat typen är densamma, men indatatypen är en två tuple med en qubit-matris som innehåller kontrollens qubit (s) som det första elementet och argumenten för den ursprungliga åtgärden som det andra elementet.
Den nya åtgärden stöder `Controlled` och stöder `Adjoint` om och endast om den ursprungliga åtgärden utfördes.

Om den ursprungliga åtgärden bara tog ett enda argument, kommer singleton-tupel att visas här.
Till exempel `Controlled X` är den kontrollerade versionen av `X` åtgärden. 
`X`har typen `(Qubit => Unit is Adj + Ctl)` , så `Controlled X` har typ `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; på grund av singleton tuple-motsvarigheten är detta samma som `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Kom ihåg att omsluta motsvarande argument för den kontrollerade versionen av åtgärden inom parentes för att konvertera dem till en tupel om bas åtgärden tog flera argument.
Till exempel `Controlled Rz` är den kontrollerade versionen av `Rz` åtgärden. 
`Rz`har typen `((Double, Qubit) => Unit is Adj + Ctl)` , så `Controlled Rz` har typen `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Därför `Controlled Rz(controls, (0.1, target))` är det ett giltigt anrop till `Controlled Rz` (Observera parenteser runt `0.1, target` ).

Ett annat exempel `CNOT(control, target)` kan implementeras som `Controlled X([control], target)` . Om ett mål ska styras av 2 Control qubits (CCNOT) kan vi använda- `Controlled X([control1, control2], target)` instruktionen.

#### `Controlled Adjoint` 

`Controlled`Och `Adjoint` functors återkommer, så det finns ingen skillnad mellan att tillämpa `Controlled Adjoint Op` eller `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Definiera kontrollerade och intilliggande implementeringar

I de första åtgärds deklarations exemplen ovan `BitFlip` har åtgärderna och `DecodeSuperdense` definierats med signaturer respektive `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` .
Eftersom `DecodeSuperdense` omfattar mätningar är det inte en enhetlig åtgärd och därför kan ingen kontrollerad icke-angränsande specialisering finnas (återkalla det relaterade kravet att en sådan åtgärd returnerar `Unit` ).
Men eftersom `BitFlip` bara utför den enda <xref:microsoft.quantum.intrinsic.x> driften kan vi ha definierat det med båda specialiseringarna.

Här beskrivs hur du kan inkludera förekomst av specialiseringar i dina deklarationer för Q #-åtgärder, vilket ger dem möjlighet att anropas tillsammans med `Adjoint` och/eller `Controlled` functors.
[Nedan](#circumstances-for-validly-defining-specializations)beskrivs några av de situationer där det är antingen giltigt eller inte giltigt för att deklarera vissa specialiseringar.

Åtgärds egenskaper definierar vilka typer av functors som kan tillämpas på den deklarerade åtgärden och vilken effekt de har. Förekomsten av dessa specialiseringar kan deklareras som en del av åtgärdens signatur, särskilt genom en anteckning med drift egenskaper: `is Adj` , `is Ctl` eller `is Adj + Ctl` .
Den faktiska implementeringen av varje specialisering kan antingen *implicit* eller *uttryckligen* definieras.

### <a name="implicitly-specifying-implementations"></a>Ange implementeringar implicit

I det här fallet består bröd texten i åtgärds deklarationen enbart av standard implementeringen. Till exempel:

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
Vi kan därför använda detta för att skriva `DecodeSuperdense` exemplet ovan mer komprimerat, genom att använda det angränsande av `PrepareEntangledPair` för att omvandla Entangled-statusen tillbaka till ett unentangled-par med qubits:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Anteckningen med åtgärds egenskaperna i deklarationen är användbar för att säkerställa att kompileraren automatiskt genererar andra specialiseringar baserat på standard implementeringen. 

Det finns ett antal viktiga begränsningar som du bör tänka på när du skapar åtgärder för användning med functors.
De mest kritiska och specialiseringarna för en åtgärd som använder resultatvärdet för en annan åtgärd *kan inte* genereras automatiskt av kompilatorn, eftersom det är oklart hur du ordnar om instruktionerna i en sådan åtgärd för att få samma effekt.

Därför är det ofta användbart att uttryckligen ange de olika implementeringarna.

### <a name="explicitly-specifying-implementations"></a>Ange implementeringar explicit

Om implementeringen inte kan genereras av kompilatorn kan den uttryckligen anges. Sådana uttryckliga specialiserings deklarationer kan bestå av ett lämpligt *generations direktiv* eller en användardefinierad implementering.
Här ger vi alla möjligheter, med exempel nedan.


#### <a name="explicit-specialization-declarations"></a>Explicita specialiserings deklarationer

Q #-åtgärder kan innehålla följande uttryckliga specialiserings deklarationer:

- `body`Specialiseringen anger implementeringen av åtgärden utan att functors tillämpas.
- `adjoint`Specialiseringen anger implementeringen av åtgärden med `Adjoint` Functor tillämpad.
- `controlled`Specialiseringen anger implementeringen av åtgärden med `Controlled` Functor tillämpad.
- `controlled adjoint`Specialiseringen anger implementeringen av åtgärden med både `Adjoint` och `Controlled` functors tillämpas.
  Den här specialiseringen kan också namnges `adjoint controlled` eftersom de två functorsen går på.


En åtgärds specialisering består av en specialisering (t. ex. `body` , eller `adjoint` osv.) följt av en av följande:

- En explicit deklaration enligt beskrivningen nedan.
- Ett *direktiv* som talar om för kompileraren *hur* du genererar specialiseringen, en av:
  - `intrinsic`, som anger att specialiseringen tillhandahålls av mål datorn.
  - `distribute`, som kan användas med- `controlled` och- `controlled adjoint` specialiseringarna.
    När det används med `controlled` anger det att kompilatorn ska beräkna specialiseringen genom att tillämpa `Controlled` på alla åtgärder i `body` .
    När det används med `controlled adjoint` anger det att kompilatorn ska beräkna specialiseringen genom att tillämpa `Controlled` på alla åtgärder i `adjoint` specialiseringen.
  - `invert`, som anger att kompilatorn ska beräkna `adjoint` specialiseringen genom att invertera `body` , d.v.s. ändra ordningen på åtgärder och tillämpa den angränsande till var och en.
    När det används med `adjoint controlled` anger detta att kompilatorn ska beräkna specialiseringen genom att invertera `controlled` specialisering.
  - `self`, för att ange att den angränsande specialiseringen är samma som `body` specialiseringen.
    Detta är giltigt för- `adjoint` och- `adjoint controlled` specialiseringarna.
    För `adjoint controlled` , `self` förutsätter att `adjoint controlled` specialiseringen är samma som `controlled` specialiseringen.
  - `auto`, för att ange att kompilatorn ska välja ett lämpligt direktiv att tillämpa.
    `auto`får inte användas för `body` specialisering.

Direktiven och `auto` alla kräver ett avslutande semikolon `;` .
`auto`Direktivet matchar följande generations direktiv om en explicit deklaration av `body` tillhandahålls:

- `adjoint`Specialiseringen skapas enligt direktivet `invert` .
- `controlled`Specialiseringen skapas enligt direktivet `distribute` .
- `adjoint controlled`Specialiseringen skapas enligt direktivet `invert` om en explicit deklaration för `controlled` har givits men inte en för `adjoint` , och `distribute` annars.

> [!TIP]   
> Om en åtgärd är självständig kan du uttryckligen ange antingen den angränsande eller den kontrollerade intill-specialiseringen via generations direktivet `self` så att kompilatorn kan använda den informationen i optimerings syfte.

En specialiserings deklaration som innehåller en användardefinierad implementering består av en argument tupel följt av ett instruktions block med den Q #-kod som implementerar specialiseringen.
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

Koden `PrepareEntangledPair` ovan motsvarar exempelvis koden nedan med explicita specialiserings deklarationer: 

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

Om kompileraren inte kan generera implementeringen för en viss specialisering automatiskt, eller om en effektivare implementering kan ges, kan implementeringen också definieras manuellt.

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
I exemplet ovan `adjoint invert;` anger att den angränsande specialiseringen ska genereras genom att invertera bröd texten och att `controlled adjoint invert;` det visar sig att den kontrollerade intilliggande specialiseringen ska genereras genom att den angivna implementeringen av den kontrollerade specialisering inverteras.

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

Det är tillåtet att ange en åtgärd utan angränsande eller kontrollerade versioner. Till exempel har mått åtgärderna ingen, eftersom de inte är inverteras eller kontrollerbara.

En åtgärd har stöd för `Adjoint` och/eller `Controlled` functors om dess deklaration innehåller en implicit eller explicit deklaration av respektive specialisering.

En explicit deklarerad angränsande och kontrollerad specialisering innebär att det finns en angränsande/kontrollerad specialisering. 

För en åtgärd vars brödtext innehåller upprepnings-till-lyckade-slingor, set-instruktioner, mätningar, retur-instruktioner eller anrop till andra åtgärder som inte stöder `Adjoint` Functor, genererar automatiskt en angränsande specialisering efter `invert` eller- `auto` direktivet.

För en åtgärd vars brödtext innehåller anrop till andra åtgärder som inte stöder Functor går det `Controlled` inte att skapa en kontrollerad specialisering automatiskt efter `distribute` eller- `auto` direktivet.

#### <a name="controlled-adjoint"></a>Kontrollerat från det intilliggande

Den kontrollerade, intilliggande versionen av en åtgärd anger hur en Quantum-kontrollerad version av åtgärdens angränsande funktion implementeras.
Det är tillåtet att ange en åtgärd utan kontrollerad version. till exempel har mått åtgärderna ingen kontrollerad, angränsande version eftersom de varken kan styras eller inverteras.

En kontrollerad, angränsande specialisering för en åtgärd måste finnas om och endast om både en intilliggande och en kontrollerad specialisering finns. I så fall härleds förekomsten av den kontrollerade angränsande specialiseringen och en lämplig specialisering genereras av kompilatorn om ingen implementering har definierats explicit. 

För en åtgärd vars brödtext innehåller anrop till andra åtgärder som inte har en kontrollerad, intilliggande version, genererar automatiskt en angränsande specialisering efter `invert` , `distribute` eller så `auto` är direktivet inte möjligt.


### <a name="type-compatibility"></a>Skriv kompatibilitet

En åtgärd med ytterligare functors som stöds kan användas överallt där en åtgärd har färre functors men samma signatur förväntas.
Till exempel kan en åtgärd av typen `(Qubit => Unit is Adj)` användas överallt där en åtgärd av typen `(Qubit => Unit)` är förväntad.

Q # är *samvariant* med avseende på anrops bara Retur typer: ett anrop som returnerar en typ `'A` är kompatibelt med ett anrop med samma Indatatyp och en resultat typ som `'A` är kompatibel med.

Q # är *contravariant* med avseende på indatatyper: ett anrop som tar en typ `'A` som indatatyp är kompatibelt med ett anrop med samma resultat typ och en indatatyp som är kompatibel med `'A` .

Det innebär att man får följande definitioner:

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

följande är sant:

- Funktionen `ConjugateInvertWith` kan anropas med ett `inner` argument i antingen `Invert` eller `ApplyUnitary` .
- Funktionen `ConjugateUnitaryWith` kan anropas med ett `inner` argument av `ApplyUnitary` , men inte `Invert` .
- Ett värde av typen `(Qubit[] => Unit is Adj + Ctl)` kan returneras från `ConjugateInvertWith` .

> [!IMPORTANT]
> Q # 0,3 introducerade en betydande skillnad i beteendet för användardefinierade typer.

Användardefinierade typer behandlas som en omsluten version av den underliggande typen, i stället för som en undertyp.
Det innebär att ett värde för en användardefinierad typ inte kan användas om ett värde av den underliggande typen förväntas.


### <a name="conjugations"></a>Conjugations

Till skillnad från klassiska bitar är det något mer engagerande att frigöra Quantum-minne eftersom qubits kan ha oönskade effekter på den återstående beräkningen om qubits fortfarande är Entangled. Detta kan undvikas genom att du avregistrerar utförda beräkningar innan du frigör minnet. Ett vanligt mönster i Quantum Computing är därför följande: 

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

Från och med vår 0,9-version har vi stöd för en conjugation-instruktion som implementerar omvandlingen ovan. Med den här instruktionen `ApplyWith` kan åtgärden implementeras på följande sätt:

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
En sådan conjugation-instruktion är självklart mycket mer användbar om den yttre och inre omvandlingen inte är tillgänglig som åtgärder, men är i stället bekvämare att beskriva genom ett block som består av flera instruktioner. 

Den inverterade omvandlingen för de instruktioner som definierats inom blocket genereras automatiskt av kompileraren och körs när Apply-blocket har slutförts.
Eftersom alla föränderligt-variabler som används som en del av inom-blocket inte kan bindas om i Apply-blocket, garanteras den genererade omvandlingen som det angränsande av beräkningen i avsnittet-block. 


## <a name="defining-new-functions"></a>Definiera nya funktioner

Functions är helt deterministiska, klassiska rutiner i Q #, som skiljer sig från åtgärder i så att de inte får ha några effekter utöver att beräkna ett utdata-värde.
I synnerhet kan funktioner inte anropa åtgärder. agera på, allokera eller låna qubits; exempel på slumpmässiga siffror; eller på annat sätt är beroende av ett tillstånd bortom indatavärdet till en funktion.
Som en följd är Q #-funktioner *rena*, där de alltid mappar samma indatavärden till samma utdata-värden.
På så sätt kan Q #-kompilatorn ändra ordning på hur och när-funktioner anropas när de genererar drifts specialiseringar.

Varje Q #-källfil kan definiera valfritt antal funktioner.
Funktions namn måste vara unika inom ett namn område och kan inte vara i konflikt med åtgärds-eller typnamn.

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

När det är möjligt är det bra att skriva ut klassisk logik i termer av funktioner i stället för åtgärder, så att den kan användas mer i drift.
Om vi till exempel hade skrivit `Square` deklarationen ovan som en *åtgärd*, skulle kompileraren inte ha kunnat garantera att anropet till den med samma indata skapar samma utdata konsekvent.

Om du vill ta del av skillnaden mellan funktioner och åtgärder bör du tänka på problemet med att slumpmässigt sampla ett slumpmässigt tal från en Q #-åtgärd:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Varje tid som `U` anropas har den en annan åtgärd `target` .
I synnerhet kan kompileraren inte garantera att om vi har lagt till en `adjoint auto` specialisering `U` -deklaration i fungerar den `U(target); Adjoint U(target);` som identitet (det vill säga som en no-OP).
Detta strider mot definitionen av det angränsande som vi såg i [vektorer och matriser](xref:microsoft.quantum.concepts.vectors), till exempel för att automatiskt generera en angränsande specialisering i en åtgärd där vi har anropat åtgärden <xref:microsoft.quantum.math.randomreal> skulle bryta mot de garantier som tillhandahålls av kompilatorn. <xref:microsoft.quantum.math.randomreal> är en åtgärd för vilken det inte finns något angränsande eller styrd version.

Å andra sidan är det möjligt att tillåta funktions anrop som `Square` är säkra, eftersom kompileraren kan vara säker på att den bara behöver bevara indatan för `Square` att hålla dess utdata stabil.
Att isolera så mycket klassisk logik som möjligt i functions gör det lätt att återanvända den logiken i andra funktioner och åtgärder.


## <a name="generic-type-parameterized-callables"></a>Generisk (typ Parameterad) Callables

Många funktioner och åtgärder som vi kanske vill definiera stämmer inte överens med typerna av deras indata, utan att bara implicit använda sina typer via en annan funktion eller åtgärd.
Anta till exempel att *mappnings* konceptet är gemensamt för många funktionella språk; med en Function $f (x) $ och en samling värden $ \{ x_1, x_2, \dots, x_n \} $, returnerar kartan en ny samling $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.
För att implementera detta i Q # kan vi dra nytta av att funktionerna är första klass.
Låt oss skriva ut ett snabbt exempel på `Map` , med ★ som plats hållare medan vi tar reda på vilka typer vi behöver.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

OBS! den här funktionen ser mycket likadan ut oavsett vilka faktiska typer som vi ersätter i.
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

Vi kan i princip skriva en version av `Map` för varje par av typer som vi stöter på, men detta ger ett antal svårigheter.
Om vi till exempel hittar ett fel i `Map` måste vi se till att korrigeringen tillämpas enhetligt i alla versioner av `Map` .
Om vi konstruerar en ny tupel eller UDT, måste du dessutom också skapa en ny `Map` för att gå vidare med den nya typen.
Även om det här är ett litet antal sådana funktioner, och vi samlar in fler och fler funktioner i samma formulär som `Map` , blir kostnaden för att introducera nya typer orimligt stor i relativt kort ordning.

Mycket av detta problem, men från att vi inte har gett kompilatorn den information som krävs för att identifiera hur de olika versionerna av `Map` är relaterade.
Vi vill att kompilatorn ska behandla `Map` som en typ av matematisk funktion från q # *typer* till q # functions.

Den här begreppet är formell genom att tillåta att funktioner och åtgärder har *typ parametrar*, samt deras vanliga tuple-parametrar.
I exemplen ovan vill vi tänka på att `Map` ha typ parametrar `Int, Pauli` i det första fallet och `Double, String` i det andra fallet.
För det mesta kan dessa typ parametrar sedan användas som om de var vanliga: vi använder värden av typen parametrar för att skapa matriser och tupler, anropa funktioner och åtgärder och tilldela till vanliga variabler eller föränderligt.

> [!NOTE]
> Det mest extrema fallet med indirekt beroende är att av qubits, där ett Q #-program inte kan förlita sig på typen av struktur `Qubit` , men **måste** skicka sådana typer till andra funktioner och funktioner.

I exemplet ovan kan vi se att vi måste `Map` ha typ parametrar, ett för att representera indata till `fn` och ett som representerar resultatet från `fn` .
I Q # skrivs detta genom att lägga till vinkelparenteser (det vill säga att `<>` inte bromsar $ \braket {} $!) efter namnet på en funktion eller åtgärd i dess deklaration, och genom att ange varje typ parameter.
Namnet på varje typ parameter måste börja med en Ticket `'` , vilket indikerar att det är en typ parameter och inte en vanlig typ (kallas även *konkret* typ).
För `Map` , skriver vi därför:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Observera att definitionen av `Map<'Input, 'Output>` ser ut ungefär likadant ut som de versioner vi skrev ut tidigare.
Den enda skillnaden är att vi uttryckligen har informerat kompilatorn som `Map` inte direkt är beroende av vad `'Input` och `'Output` är, men fungerar för två typer genom att använda dem indirekt genom `fn` .
När vi har definierat `Map<'Input, 'Output>` på det här sättet kan vi anropa det som om det var en vanlig funktion:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Att skriva allmänna funktioner och åtgärder är en plats där "tupel-in-tupel" är ett mycket användbart sätt att tänka på när det gäller Q #-funktioner och-åtgärder.
> Eftersom varje funktion tar exakt en indata och returnerar exakt en utdata, matchar en indata av typen `'T -> 'U` *valfri* Q #-funktion.
> På samma sätt kan alla åtgärder skickas till inmatad typ `'T => 'U` .

Som ett andra exempel bör du tänka på utmaningen med att skriva en funktion som returnerar kompositionen av två andra funktioner:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Här måste vi ange exakt vad `A` , `B` och `C` är, och därmed begränsa verktyget för vår nya `Compose` funktion.
Efter alla är det `Compose` bara beroende av `A` , `B` , och `C` *via* `innerFn` och `outerFn` .
Alternativt kan vi lägga till typ parametrar som `Compose` anger att det fungerar för *alla* `A` , `B` och `C` , så länge parametrarna matchar de som förväntas av `innerFn` och `outerFn` :

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Standard biblioteken för Q # innehåller en mängd olika typer av typ parametrar och funktioner som gör det lättare att uttrycka ett kontroll flöde med högre ordning.
Dessa beskrivs ytterligare i guiden för [Q # standard library](xref:microsoft.quantum.libraries.standard.intro).


## <a name="callables-as-first-class-values"></a>Callables som värden i den första klassen

En viktig teknik för uppföljning av kontroll flöde och klassisk logik med hjälp av funktioner i stället för åtgärder är att använda dessa åtgärder och funktioner i Q # är *första-klass*.
Det innebär att de är varje värde på språket i sin egen rätt.
Följande är till exempel en perfekt giltig Q #-kod, om en liten indirekta:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

Värdet för variabeln `ourH` i kodfragmentet ovan är sedan åtgärden <xref:microsoft.quantum.intrinsic.h> , så att vi kan anropa det värdet som vilken annan åtgärd som helst.
På så sätt kan vi skriva åtgärder som utför åtgärder som en del av deras indata, vilket utgör en högre ordning för kontroll flödes koncept.
Vi kan till exempel föreställa oss en åtgärd genom att använda den två gånger för samma mål-qubit.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Returnera åtgärder från en funktion

Vi betonar att vi även kan returnera åtgärder som en del av utdata, så att vi kan isolera vissa typer av klassisk villkorlig logik som en klassisk funktion som returnerar en beskrivning av ett Quantum-program i form av en åtgärd.
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

Den här nya funktionen är en funktion, där om vi anropar den med samma värden `hereBit` och `thereBit` , kommer vi alltid att få tillbaka samma åtgärd.
Därför kan avkodaren köras inuti åtgärder utan att du behöver tänka på hur avkodnings logiken interagerar med definitionerna för de olika specialiseringarna för åtgärder.
Det vill säga att vi har isolerat den klassiska logiken i en funktion, vilket garanterar att den kompilerare som funktions anropet kan ordnas om med impunity, så länge som indatamängden bevaras.


## <a name="partial-application"></a>Partiellt program

Vi kan göra mycket mer med funktioner som returnerar åtgärder med hjälp av *partiella program*, där vi kan tillhandahålla en eller flera delar av indatamängden för en funktion eller åtgärd utan att faktiskt anropa det. Till exempel kan vi, om du `ApplyTwice` vill, anropa exemplet ovan, ange att vi inte vill ange, till och med vilka qubit ingångs åtgärden ska gälla:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

I det här fallet innehåller den lokala variabeln `twiceOp` den delvis tillämpade åtgärden `ApplyTwice(op, _)` , där delar av de inmatade värden som ännu inte har angetts anges av `_` .
När vi faktiskt ringer `twiceOp` på nästa rad, skickas som intill den delvis tillämpade åtgärden alla återstående delar av indatamängden till den ursprungliga åtgärden.
Därför är ovanstående kodfragment detsamma som att ha anropat `ApplyTwice(op, target)` direkt, Spara för att vi har infört en ny lokal variabel som gör det möjligt för oss att försena anropet och tillhandahålla vissa delar av indatan.

Eftersom en åtgärd som har tillämpats delvis inte anropas förrän hela indatan har tillhandahållits, kan vi på ett säkert sätt tillämpa åtgärder även inifrån functions.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

I princip skulle den klassiska logiken i `SquareOperation` ha varit mycket mer engagerad, men den är fortfarande isolerad från resten av en åtgärd av de garantier som kompileraren kan erbjuda om functions.
Den här metoden kommer att användas i ett standard bibliotek i Q # för att uttrycka klassiskt kontroll flöde på ett sätt som kan användas i Quantum-program.


## <a name="recursion"></a>Rekursion

Q # callables kan vara direkt eller indirekt rekursivt.
Det vill säga en åtgärd eller funktion kan anropa sig själv, eller så kan den anropa ett annat anrop som direkt eller indirekt anropar den anropande åtgärden.

Det finns två viktiga kommentarer om användningen av rekursion, men:

- Användningen av rekursion i åtgärder är sannolikt att störa vissa optimeringar.
  Detta kan ha en betydande inverkan på körnings tiden för algoritmen.
- Vid körning på en faktisk Quantum-enhet kan stack utrymmet vara begränsat och så att djup rekursion kan leda till ett körnings fel.
  I synnerhet identifierar inte Q #-kompilatorn och körnings miljön och optimerar slut rekursion.

## <a name="next-steps"></a>Nästa steg

Lär dig mer om [variabler](xref:microsoft.quantum.guide.variables) i Q #.