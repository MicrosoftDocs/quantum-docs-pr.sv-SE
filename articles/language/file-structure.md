---
title: 'Q # fil struktur'
description: 'Lär dig hur du strukturerar namn områden och åtgärder, funktioner och användardefinierade deklarationer i Q #-program och-bibliotek.'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b4bb7d4d70677dbd5d921a9f68313760499a56a1
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907400"
---
# <a name="file-structure"></a>Filstruktur

En Q #-fil består av en sekvens med namn områdes deklarationer.
Varje namn områdes deklaration innehåller deklarationer för användardefinierade typer, åtgärder och funktioner.
En namn områdes deklaration får innehålla valfritt antal av varje typ av deklaration, och i vilken ordning som helst.
Den enda text som kan visas utanför en namn områdes deklaration är kommentarer.
I synnerhet är dokumentations kommentarer för ett namn område före deklarationen.

## <a name="namespace-declarations"></a>Namn områdes deklarationer

En Q #-fil har vanligt vis exakt en namn områdes deklaration, men kan ha ingen (och vara tom eller bara innehålla kommentarer) eller innehålla flera namn områden.
Namespace-deklarationer får inte vara kapslade.

Samma namnrymd kan deklareras i flera Q #-filer som kompileras tillsammans, så länge det inte finns någon typ, åtgärd eller funktions deklaration med samma namn.
I synnerhet är det inte tillåtet att definiera samma typ i samma namnrymd i flera filer, även om deklarationerna är identiska.

En namn områdes deklaration består av nyckelordet `namespace`följt av namnet på namn området, en öppen klammerparentes `{`, de deklarationer som finns i namn området och en avslutande klammerparentes `}`.
Namn områdes namn följer .NET-mönstret för en sekvens med en eller flera juridiska symboler avgränsade med punkter `.`.
`MyQuantumStuff` och `Microsoft.Quantum.Canon` är till exempel giltiga namn rymds namn.
Enligt konvention är symbolerna i namn områdes namnet versaler, men det är inget krav.

Deklarationer kan visas i valfri ordning i en namn områdes deklaration.
Referenser till typer eller callables som deklarerats senare i en fil löses korrekt. Det finns inget behov av typen, åtgärden eller funktions deklarationen att föregå en referens till den.

## <a name="open-directives"></a>Öppna direktiv

I ett namn områdes block kan `open`-direktivet användas för att importera alla typer och callables som definierats i ett visst namn område och referera till dem med hjälp av okvalificerade namn. 

Ett sådant `open`-direktiv består av `open` nyckelord, följt av namn området som ska öppnas och ett avslutande semikolon.

Till exempel,

```qsharp
open Microsoft.Quantum.Canon;
```

Alternativt kan ett kort namn för det öppna namn området definieras så att alla element från det namn området kan (och behöver) kvalificeras av det definierade korta namnet. Ett sådant kort namn definieras genom att nyckelordet läggs `as` följt av det önskade korta namnet före semikolonet i ett `open`-direktiv:

```qsharp
open Microsoft.Quantum.Math as Math;
```

Alla `open`-direktiv måste finnas före eventuella `function`-, `operation`-eller `newtype`-deklarationer i namn områdes blocket.
`open`-direktivet gäller hela namn områdes blocket i en fil.

## <a name="user-defined-type-declarations"></a>Användardefinierade typ deklarationer

Q # gör det möjligt för användare att deklarera nya användardefinierade typer, enligt beskrivningen i avsnittet om [typ modell för Q](xref:microsoft.quantum.language.type-model) .
Användardefinierade typer är distinkta även om bas typerna är identiska.
I synnerhet finns det ingen automatisk konvertering mellan värden av två användardefinierade typer, även om de underliggande typerna är identiska.

En användardefinierad typ deklaration består av nyckelordet `newtype`följt av namnet på den användardefinierade typen, en `=`, en giltig typ specifikation och ett avslutande semikolon.

Några exempel:

```qsharp
newtype PairOfInts = (Int, Int);
```

Varje Q #-källfil kan deklarera ett valfritt antal användardefinierade typer.
Typnamn måste vara unika inom ett namn område och kan inte vara i konflikt med funktions-och funktions namn.

Det går inte att definiera cirkulära beroenden mellan användardefinierade typer. Rekursiva typer är därför inte möjliga inom Q #.

## <a name="operation-declarations"></a>Åtgärds deklarationer

Åtgärder är kärnan i Q #, ungefär likvärdiga med funktioner på andra språk.
Varje Q #-källfil kan definiera valfritt antal åtgärder.

Åtgärds namn måste vara unika inom ett namn område och får inte stå i konflikt med typ-och funktions namn.

En åtgärds deklaration består av nyckelordet `operation`, följt av symbolen som är åtgärdens namn, en typ av identifierare som definierar argumenten för åtgärden, ett kolon `:`, en typ anteckning som beskriver åtgärdens resultat typ, eventuellt en anteckning med åtgärds egenskaper, en öppen klammer `{`, bröd texten i åtgärds deklarationen och en avslutande klammerparentes `}`.

Bröd texten i åtgärds deklarationen består antingen av standard implementeringen eller en lista över specialiseringar.
Standard implementeringen kan anges direkt i deklarationen om endast implementeringen av standard-specialisering måste anges explicit.
I det här fallet är en anteckning med åtgärds egenskaperna i deklarationen användbar för att säkerställa att kompileraren automatiskt genererar andra specialiseringar baserat på standard implementeringen. 

Exempel 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

Åtgärds egenskaper definierar vilka typer av functors som kan tillämpas på den deklarerade åtgärden och vilken effekt de har. Om en åtgärd implementerar en enhetlig omvandling, är det möjligt att definiera hur åtgärden fungerar när *adjointed* eller *kontrol leras*.
Förekomsten av dessa specialiseringar kan deklareras som en del av åtgärdens signatur. Motsvarande implementering för varje sådan implicit deklarerad specialisering genereras sedan av kompileraren. I exemplet ovan genereras ett intilliggande, en styrd och en kontrollerad angränsande specialisering av kompileraren. 

Om implementeringen inte kan genereras av kompilatorn kan den uttryckligen anges. Sådana uttryckliga specialiserings deklarationer kan antingen bestå av ett lämpligt generations direktiv som klargör hur en viss specialisering ska skapas eller en användardefinierad implementering. Koden i `PrepareEntangledPair` ovan motsvarar exempelvis koden nedan som innehåller explicita specialiserings deklarationer: 

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
Om kompilatorn inte kan generera implementeringen för en viss specialisering utan ytterligare instruktioner, som ett mer exakt generations direktiv, eller om en effektivare implementering kan ges, kan implementeringen också definieras manuellt.

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

För att en åtgärd ska kunna stödja program av `Adjoint` och/eller `Controlled` Functor måste dess returtyp nödvändigt vis `Unit`. 


### <a name="explicit-specialization-declarations"></a>Explicita specialiserings deklarationer

Q #-åtgärder kan innehålla följande uttryckliga specialiserings deklarationer:

- `body` specialisering anger implementeringen av åtgärden utan att functors tillämpas.
- `adjoint` specialisering anger implementeringen av åtgärden med den `Adjoint` Functor som tillämpas.
- `controlled` specialisering anger implementeringen av åtgärden med den `Controlled` Functor som tillämpas.
- `controlled adjoint` specialisering anger implementeringen av åtgärden med både `Adjoint` och `Controlled` functors tillämpas.
  Den här specialiseringen kan också ha namnet `adjoint controlled`, eftersom de två functorsna går på distans.


En åtgärds-specialisering består av en specialisering (t. ex. `body`eller `adjoint`osv.) följt av någon av följande:

- En explicit deklaration enligt beskrivningen nedan.
- Ett direktiv som talar om för kompileraren hur du genererar specialiseringen, en av:
  - `intrinsic`, som anger att specialiseringen tillhandahålls av mål datorn.
  - `distribute`som kan användas med `controlled` och `controlled adjoint` specialiseringar.
    När det används med `controlled`anger det att kompilatorn ska beräkna specialiseringen genom att tillämpa `Controlled` på alla åtgärder i `body`.
    När det används med `controlled adjoint`anger det att kompilatorn ska beräkna specialiseringen genom att tillämpa `Controlled` på alla åtgärder i `adjoint` specialisering.
  - `invert`, som anger att kompilatorn ska beräkna `adjoint` specialisering genom att invertera `body`, dvs. ändra ordningen på åtgärderna och tillämpa den angränsande i var och en.
    När det används med `adjoint controlled`anger detta att kompilatorn ska beräkna specialiseringen genom att invertera `controlled` specialisering.
  - `self`för att indikera att den angränsande specialiseringen är samma som den `body` specialiseringen.
    Detta är giltigt för `adjoint` och `adjoint controlled` specialiseringar.
    För `adjoint controlled`innebär `self` att `adjoint controlled` specialisering är samma som `controlled` specialisering.
  - `auto`för att ange att kompilatorn ska välja ett lämpligt direktiv att tillämpa.
    `auto` får inte användas för `body` specialisering.

Direktiven och `auto` alla kräver ett avslutande semikolon `;`.
`auto`-direktivet matchar följande generations direktiv om en explicit deklaration av `body` tillhandahålls:

- `adjoint` specialisering skapas enligt direktivet `invert`.
- `controlled` specialisering skapas enligt direktivet `distribute`.
- `adjoint controlled` specialisering skapas enligt direktivet `invert` om en explicit deklaration för `controlled` anges, men inte en för `adjoint`, och `distribute` annars.

> [!TIP]   
> Om en åtgärd är självständig kan du uttryckligen ange antingen den angränsande eller den kontrollerade inangränsandea specialiseringen via generationens direktiv `self` för att tillåta att kompileraren använder den informationen i optimerings syfte.

En specialiserings deklaration som innehåller en användardefinierad implementering består av en argument tupel följt av ett instruktions block med den Q #-kod som implementerar specialiseringen.
I argument listan används `...` för att representera argumenten som har deklarerats för åtgärden som helhet.
För `body` och `adjoint`bör argument listan alltid vara `(...)`; för `controlled` och `adjoint controlled`ska argument listan vara en symbol som representerar matrisen med kontroll qubits, följt av `...`, inom parentes; till exempel `(controls,...)`.

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

### <a name="adjoint"></a>Angränsande

Den angränsande av en åtgärd anger hur den komplexa konjugatet för åtgärden implementeras, d.v.s. hur åtgärden fungerar när "körs i omvänd ordning".
Det är tillåtet att ange en åtgärd utan angränsande; mätnings åtgärder har till exempel inget angränsande eftersom de inte är inverteras.
En åtgärd stöder `Adjoint` Functor om dess deklaration innehåller en implicit eller explicit deklaration av en närliggande specialisering.
En explicit deklarerad, intilliggande, intilliggande specialisering innebär att det finns en närliggande specialisering. 

För åtgärder vars brödtext innehåller upprepnings-tills-Success-slingor, set-instruktioner, mätningar, Return-instruktioner eller anrop till andra åtgärder som inte har stöd för `Adjoint` Functor, genererar automatiskt en angränsande specialisering enligt `invert`-eller `auto`-direktivet.

### <a name="controlled"></a>Styr

Den kontrollerade versionen av en åtgärd anger hur en Quantum-kontrollerad version av åtgärden implementeras, t. ex. hur en åtgärd fungerar när den tillämpas på tillståndet för ett Quantum-register.
En fullständig beskrivning finns i det [styrda](xref:microsoft.quantum.language.type-model#controlled) avsnittet.

Det är tillåtet att ange en åtgärd utan styrd version. till exempel har mått åtgärderna ingen styrd version eftersom de inte är styrda.
En åtgärd stöder `Controlled`-Functor om och endast om dess deklaration innehåller en implicit eller explicit deklaration av en kontrollerad specialisering.
En explicit deklarerad, intilliggande, intilliggande specialisering innebär att en kontrollerad specialisering förekommer. 

För en åtgärd vars brödtext innehåller anrop till andra åtgärder som inte stöder `Controlled` Functor, genererar automatiskt en kontrollerad specialisering som följer `distribute` eller `auto` direktivet.

### <a name="controlled-adjoint"></a>Kontrollerat från det intilliggande

Den kontrollerade, intilliggande versionen av en åtgärd anger hur en Quantum-kontrollerad version av åtgärdens angränsande funktion implementeras.
Det är tillåtet att ange en åtgärd utan kontrollerad version. till exempel har mått åtgärderna ingen kontrollerad, angränsande version eftersom de varken kan styras eller inverteras.

En kontrollerad, angränsande specialisering för en åtgärd måste finnas om och endast om både en intilliggande och en kontrollerad specialisering finns. I så fall härleds förekomsten av den kontrollerade angränsande specialiseringen och en lämplig specialisering genereras av kompilatorn om ingen implementering har definierats explicit. 

För en åtgärd vars brödtext innehåller anrop till andra åtgärder som inte har en kontrollerad version som inte är en kontrollerad version, genererar automatiskt en angränsande specialisering efter `invert`, `distribute` eller `auto`-direktivet inte är möjligt.


### <a name="examples"></a>Exempel

En åtgärds deklaration kan vara så enkel som följande, som definierar den primitiva Pauli X-åtgärden:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

Följande definierar Teleport-åtgärden.

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a>Funktions deklarationer

Functions är rent klassiska rutiner i Q #.
Varje Q #-källfil kan definiera valfritt antal funktioner.

En funktions deklaration består av nyckelordet `function`följt av symbolen som är funktionens namn, en typ av identifierare, en typ anteckning som beskriver funktionens returtyp och ett instruktions block som beskriver implementeringen av funktionen.

Instruktions blocket som definierar en funktion måste stå inom `{` och `}` som alla andra instruktions block.

Funktions namn måste vara unika inom ett namn område och kan inte vara i konflikt med åtgärds-och typnamn.
Funktioner får inte allokera eller låna qubits eller anropa åtgärder. En partiell tillämpning av åtgärder eller överföring av värden i åtgärds typ är bra.

Exempel:

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
