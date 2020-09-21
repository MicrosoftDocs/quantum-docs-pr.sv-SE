---
title: Q# Om
description: Grundläggande begrepp för Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 86f6538cf383f4e7c14255b38cfb1c141c8f991b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835527"
---
# <a name="no-locq-basics"></a>Q# Om

Den här artikeln innehåller en kort introduktion till de grundläggande Bygg stenarna i Q# .

En översikt över vad som Q# är och var den passar in som en grundläggande komponent i Quantum Development Kit finns i [Vad är Q# ?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Vad är ett Quantum-program?

Från ett tekniskt perspektiv är ett Quantum-program en viss uppsättning klassiska del rutiner som, vid anrop, utför vissa åtgärder på ett Quantum-system.
En viktig följd av den vyn är att ett Q# program inte direkt modellerar qubits, utan beskriver i stället hur en klassisk kontrollerad dator interagerar med dessa qubits.
Enligt design Q# definierar inte Quantum-tillstånd eller andra egenskaper för Quantum Mechanics direkt.
Anta till exempel att State $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ beskrivs i guiden för [Quantum Computing-koncept](xref:microsoft.quantum.concepts.intro) .
För att förbereda det här läget i Q# börjar du med de fakta som qubits initieras i $ \ket {0} $ State och att $ \ket{+} = H\ket {0} $, där $H $ är [Hadamard-transformeringen](xref:microsoft.quantum.glossary#hadamard), som implementeras av [ `H` åtgärden](xref:microsoft.quantum.intrinsic.h). Basic Q# -koden för att initiera och transformera en qubit och sedan se ut så här:

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
Mer information om att initiera eller *allokera*, qubits finns i [arbeta med qubits](xref:microsoft.quantum.guide.qubits).

## <a name="quantum-states-in-no-locq"></a>Quantum-tillstånd i Q#

Det tidigare programmet refererar inte uttryckligen till tillstånd inom Q# men det beskrivs hur vårt program *omvandlade* statusen.
Med den här metoden kan du helt oberoende om vad ett Quantum-tillstånd *är* på varje måldator, vilket kan ha olika tolkningar beroende på datorn. 

Ett Q# program kan inte Introspect till status för en qubit.
I stället kan ett program anropa åtgärder, till exempel [`Measure`](xref:microsoft.quantum.intrinsic.measure) för att lära sig information från en qubit och anropa åtgärder som [`X`](xref:microsoft.quantum.intrinsic.x) och [`H`](xref:microsoft.quantum.intrinsic.h) för att agera för en qubit-status.
De här *åtgärderna faktiskt görs* enbart konkret av mål datorn som används för att köra det aktuella Q# programmet.
Om du till exempel kör programmet i en [full-State-Simulator](xref:microsoft.quantum.machines.full-state-simulator)utför simulatorn motsvarande matematiska åtgärder till det simulerade Quantum-systemet.
Men om mål datorn är en verklig Quantum-dator kan du, men i framtiden, använda den här typen av åtgärder för Q# att dirigera datorn från Quantum-datorn för att utföra motsvarande *verkliga* åtgärder på det *verkliga* Quantum-systemet, till exempel exakta Timed laser pulsering.

Ett Q# program kombinerar dessa åtgärder så som de definieras av en mål dator för att skapa nya, högre åtgärder för att uttrycka Quantum-beräkning.
På det här sättet är det Q# enkelt att uttrycka logiken för de underliggande Quantum-och hybrid Quantum-algoritmerna, samtidigt som det är allmänt vad gäller strukturen i mål datorn eller simulatorn.

## <a name="no-locq-operations-and-functions"></a>Q# åtgärder och funktioner

Konkret, ett Q# program omfattar *åtgärder*, *funktioner*och alla användardefinierade typer. 

Åtgärder används för att beskriva omvandlingar av Quantum Systems och är de mest grundläggande Bygg stenarna för Q# program. Varje åtgärd som definierats i Q# kan sedan anropa valfritt antal andra åtgärder.

Till skillnad från åtgärder används funktioner för att beskriva rent *deterministiskt* klassiskt klassiskt beteende och har inga effekter, förutom att beräkna klassiska värden. Anta till exempel att du vill mäta qubits i slutet av ett program och lägga till mått resultatet i en matris.
I det här fallet `Measure` är en *åtgärd* som instruerar mål datorn att utföra en mätning på (verkliga eller simulerade) qubits. På samma gång hanterar *Functions* den klassiska processen för att lägga till de returnerade resultaten i en matris.

Åtgärder och funktioner kallas tillsammans *callables*. Deras underliggande struktur och beteende införs och beskrivs i [åtgärder och funktioner i Q# ](xref:microsoft.quantum.guide.operationsfunctions).


## <a name="no-locq-syntax-overview"></a>Q# syntax-översikt

Syntaxen för ett språk beskriver de olika kombinationer av symboler som utgör ett syntaktiskt korrekt program.
I Q# klassificeras syntax-element i tre olika grupper: typer, uttryck och uttryck.

### <a name="types"></a>Typer
Q# är ett starkt inskrivet språk, så att en noggrann användning av typer kan hjälpa kompilatorn att tillhandahålla starka garantier om Q# program vid kompilering.
Förutom standard-och Quantum-/regionsspecifika inbyggda primitiva typer, till exempel,,, `Int` `Bool` `Qubit` och `Result` , Q# ger stöd för användardefinierade typer.

För beskrivningar av alla primitiva typer, information om matris-och tupel typer och steg för att definiera nya typer i en Q# fil, se [typer Q# i ](xref:microsoft.quantum.guide.types).

### <a name="expressions"></a>Uttryck
Ett uttryck i ett programmeringsspråk är en kombination av en eller flera konstanter, variabler, operatorer och funktioner som programmerings språket tolkar och utvärderar till ett särskilt värde.
För varje typ på ett språk kan exempelvis uttryck av den typen vara antingen *litteraler* eller symboler som är kopplade till ett värde av den typen.
Till exempel `5` är en `Int` literal (vilket även ett uttryck av typen `Int` ) och om symbolen `count` är kopplad till heltal svärdet `5` är det `count` också ett heltals uttryck.

Dessutom kan ett uttryck bestå av andra uttryck som kombineras av vissa operatorer.
Till exempel ett annat `Int` uttryck som utvärderas till `5` är `2+3` .

Mer information om uttryck och kompatibla operatorer i Q# finns i [text uttryck i Q# ](xref:microsoft.quantum.guide.expressions). 

### <a name="statements"></a>Instruktioner 
En instruktion är en syntaktisk enhet av ett tvingande programmeringsspråk som uttrycker en åtgärd som ska utföras. Uttryck med uttryck i dessa instruktioner returnerar inte resultat och körs bara för deras sido effekter. Uttryck returnerar dock alltid ett resultat och har ofta inga sido effekter. I korthet Q# körs instruktioner, medan uttryck utvärderas.

Ett enkelt exempel på en instruktion i Q# är att tilldela en symbol till ett uttryck:
```qsharp
let count = 5;
```

Ett mer intressant exempel är en `for` instruktion som stöder iteration och innehåller ett *instruktions block*.
Anta `qubits` att är symbolen knuten till ett register över qubits (tekniskt av typen `Qubit[]` eller en matris av `Qubit` typer). Dra
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
är en instruktion som itererar över varje qubit i registret, vilket utför `H` åtgärden på var och en. Observera att `H(qubit);` även är en instruktion i sig själv.

Du kan använda valfritt anrops uttryck av typen `Unit` (en `Unit` typ returnerar ingen information) som en instruktion.
Den här typen av uttryck är användbar när du anropar åtgärder på qubits som returneras `Unit` eftersom syftet med instruktionen är att ändra det implicita Quantum-läget.
Uttrycks utvärderings uttryck kräver ett avslutande semikolon.

Du använder instruktioner för att bygga nästan varje aspekt av ett Q# program, och ingen enskild sida kan omfatta all information som rör dem.
Mer information om deras lexikala struktur och formatering finns i [ Q# fil strukturen](xref:microsoft.quantum.guide.filestructure). för symbol bindnings tilldelning och omfång, se [variabler Q# i ](xref:microsoft.quantum.guide.variables)och för kontroll flödes slingor som `for` , se [kontroll flöde i Q# ](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Nästa steg

Börja lära dig om [typer Q# i ](xref:microsoft.quantum.guide.types).

Mer bakgrund om grunderna och motivation bakom Q# finns i [Varför behöver vi Q# ?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
