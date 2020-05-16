---
title: 'Q #-grunder'
description: 'Grundläggande begrepp för Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: fd0ea47f00b1456ec460808ef7d451c8427677cd
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431163"
---
# <a name="q-basics"></a>Q #-grunder

I det här avsnittet presenterar vi en kort introduktion till de grundläggande Bygg stenarna för Q #.

En snabb översikt över vad Q # är och var det passar in som en grundläggande komponent i Quantum Development Kit, kan du titta på [Vad är Q #?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Vad är ett Quantum-program?

Från ett tekniskt perspektiv kan ett Quantum-program ses som en viss uppsättning klassiska under rutiner som, vid anrop, utför vissa åtgärder på ett Quantum-system.
En viktig följd av den vyn är att ett program som skrivits i Q # inte direkt modellerar qubits själva, utan beskriver i stället hur en klassisk kontroll dator interagerar med dessa qubits.
Enligt design definierar Q # alltså inte Quantum-tillstånd eller andra egenskaper för Quantum Mechanics direkt.
Anta till exempel att State $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ beskrivs i guiden för [Quantum Computing-koncept](xref:microsoft.quantum.concepts.intro) .
För att förbereda det här läget i Q #, använder vi de fakta som qubits initieras i $ \ket {0} $ State och att $ \ket{+} = H\ket {0} $, där $H $ är Hadamard-transformeringen, som implementeras av [ `H` åtgärd] (] (XREF: Microsoft. Quantum. inre. H):

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a>Quantum-tillstånd i Q #

Det är viktigt att i Skriv programmet ovan inte uttryckligen referera till statusen inom Q #, utan att i stället se hur tillstånd har *omvandlats* av vårt program.
På så sätt kan vi helt oberoende om vad ett Quantum-tillstånd *är* även på varje måldator, vilket kan ha olika tolkningar beroende på datorn. 

Ett Q #-program kan inte Introspect till en qubit.
Ett program kan istället anropa åtgärder, till exempel [`Measure`](xref:microsoft.quantum.intrinsic.measure) för att lära sig information från en qubit och anropa åtgärder som [`X`](xref:microsoft.quantum.intrinsic.x) och [`H`](xref:microsoft.quantum.intrinsic.h) för att agera för en qubit.
De här *åtgärderna faktiskt görs* enbart konkret av mål datorn som vi använder för att köra ett visst Q #-program.
Om du till exempel kör programmet i hela den här [simulatorn](xref:microsoft.quantum.machines.full-state-simulator)utför simulatorn motsvarande matematiska åtgärder till det simulerade Quantum-systemet.
Men om mål datorn är en verklig Quantum-dator och du tittar på framtiden, så dirigerar de här åtgärderna i Q # den Quantum datorn för att utföra motsvarande *verkliga* åtgärder på det *verkliga* Quantum-systemet (t. ex. exakta tids bara laser pulser).

Ett Q #-program kombinerar dessa åtgärder så som definieras av en mål dator för att skapa nya, högre åtgärder för att uttrycka Quantum-beräkning.
På så sätt gör Q # det enkelt att uttrycka logiken för de underliggande Quantum-och hybrid Quantum-algoritmerna, samtidigt som det är allmänt vad gäller strukturen för en mål dator eller Simulator.

## <a name="q-operations-and-functions"></a>Q #-åtgärder och-funktioner

Konkret är ett Q #-program bestående av *åtgärder*, *funktioner*och andra användardefinierade typer. 

Åtgärder används för att beskriva omvandlingar av Quantum Systems och är de mest grundläggande Bygg stenarna för Q #-program. Varje åtgärd som definierats i Q # kan sedan anropa valfritt antal andra åtgärder.

Till skillnad från åtgärder används funktioner för att beskriva rent *deterministiskt* klassiskt klassiskt beteende och har inga effekter, förutom att beräkna klassiska värden. Anta till exempel att vi vill mäta våra qubits i slutet av ett program och lägga till mått resultatet i en matris.
I det här fallet `Measure` är en *åtgärd* som instruerar mål datorn att utföra en mätning på (verklig eller simulerad) qubits, och den klassiska processen för att lägga till de returnerade resultaten i en matris hanteras av *Functions*.

Åtgärder och funktioner kallas för *callables*, och deras underliggande struktur och beteende införs på sidan [åtgärder och funktioner på Q #](xref:microsoft.quantum.guide.operationsfunctions) .


## <a name="q-syntax-overview"></a>Översikt över Q # syntax

Syntaxen för ett språk beskriver de olika kombinationer av symboler som utgör ett syntaktiskt korrekt program.
I Q # kan vi klassificera elementen i dess syntax i tre olika grupper: typer, uttryck och uttryck.

### <a name="types"></a>Typer
Q # är ett starkt skrivet språk, så att en noggrann användning av typer kan hjälpa kompilatorn att tillhandahålla starka garantier för Q #-program vid kompilering.
Förutom standard-och Quantum-/regionsspecifika inbyggda primitiva typer (t. ex.,, `Int` `Bool` `Qubit` och `Result` ) ger Q # stöd för användardefinierade typer.
Alla typer av olika typer av Q # beskrivs på sidan [typer i Q #](xref:microsoft.quantum.guide.types) , tillsammans med information om matris-och tuple-typer, samt hur du definierar nya typer i en Q #-fil.

### <a name="expressions"></a>Uttryck
Ett uttryck i ett programmeringsspråk är en kombination av en eller flera konstanter, variabler, operatorer och funktioner som programmerings språket tolkar och utvärderar till ett särskilt värde.
För varje typ på ett språk kan exempelvis uttryck av den typen vara antingen *litteraler* eller symboler som är kopplade till ett värde av den typen.
Till exempel `5` är en `Int` literal (vilket även ett uttryck av typen `Int` ) och om symbolen `count` är kopplad till heltal svärdet `5` är det `count` också ett heltals uttryck.

Dessutom kan ett uttryck bestå av andra uttryck tillsammans med vissa operatorer.
Ett annat exempel på ett `Int` uttryck som utvärderas till `5` är `2+3` .

De möjliga uttrycken av typer i Q #, samt de kompatibla operatorer som kan användas för att forma dem, beskrivs i [typ uttrycken på Q #](xref:microsoft.quantum.guide.expressions) -sidan. 

### <a name="statements"></a>Instruktioner 
En instruktion är en syntaktisk enhet av ett tvingande programmeringsspråk som uttrycker åtgärder som ska utföras. Uttryck med uttryck i dessa instruktioner returnerar inte resultat och utförs enbart för sina sido effekter, medan uttryck alltid returnerar ett resultat och ofta inte har sido effekter alls.
Denna åtskillnad observeras ofta i formuleringen: ett uttryck utvärderas, medan en instruktion körs.

Ett mycket grundläggande exempel på en instruktion i Q # tilldelar en symbol till ett uttryck:
```qsharp
let count = 5;
```

Ett något mer intressant exempel är den `for` instruktion som stöder iteration och innehåller ett *instruktions block*.
Anta `qubits` att är symbolen knuten till ett register över qubits (tekniskt av typen `Qubit[]` , dvs. en matris av `Qubit` typer). Dra
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
är en instruktion som itererar över varje qubit i registret, vilket utför `H` åtgärden på var och en. Observera att `H(qubit);` även är en instruktion i sig själv.

I själva verket kan alla anrops uttryck av typen `Unit` (de callables som inte returnerar information) användas som en instruktion.
Detta används främst när du anropar åtgärder på qubits som returneras `Unit` eftersom syftet med instruktionen är att ändra implicit Quantum-tillstånd.
Uttrycks utvärderings uttryck kräver ett avslutande semikolon.

Nästan alla aspekter av ett Q #-program skapas med hjälp av instruktioner, så att ingen enskild sida kan omfatta all information som rör dem.
Deras lexikala struktur och formatering beskrivs i avsnittet om [fil struktur för Q #](xref:microsoft.quantum.guide.filestructure) , symbol bindnings tilldelning och omfattning vid [variabler i q #](xref:microsoft.quantum.guide.variables)och kontroll av flödes slingor, till exempel `for` vid [kontroll flöde i q #](xref:microsoft.quantum.guide.controlflow).


## <a name="whats-next"></a>Nästa steg
I resten av den här guiden visar vi hur du använder Q # för att skapa komplexa Quantum-program genom de grundläggande Bygg stenarna för åtgärder, funktioner och typer.

Du kan börja lära dig om [typer i Q #](xref:microsoft.quantum.guide.types)för att komma igång.

Om du är intresse rad av att lära dig mer om grunderna och motivation bakom Q #, kolla [Varför behöver vi Q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
