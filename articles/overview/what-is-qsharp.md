---
title: Vad är Q# och QDK?
description: Lär dig mer om Q#, ett programmeringsspråk som skapats av Microsoft för att kunna utveckla program för kvantdatorer och som är en viktig komponent i Microsofts Quantum Development Kit
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907009"
---
# <a name="what-are-q-and-the-qdk"></a>Vad är Q# och QDK?

Q # är ett programmeringsspråk med funktioner som är särskilt utformade för användning med kvantberäkning.
Som en viktig komponent av Microsofts Quantum Development Kit (QDK) ger det ett ramverk som gör att kvantprogrammerare kan fokusera på algoritmerna utan att behöva tänka på teknisk information, till exempel optimering av grindar eller den fysiska implementeringen av en kvantdator.

QDK omfattar ett stort utbud av verktyg som ger utvecklare allt de behöver för att kunna börja skriva Quantum-program.
Vid sidan av Q#-språket innehåller QDK:
* *Q#-bibliotek*, som gör det möjligt för utvecklare att komma igång med att köra och skapa verkliga Quantum-program idag
* olika *måldatorer* där Q#-program kan köras. De innefattar resursuppskattningar och simulatorer för större Quantum-program, samt en Quantum-simulator med fullständigt tillstånd som fungerar som en brusfri Quantum-dator. Den senare är mycket användbar för att mixtra med idéer, felsökning av program och inlärning av kvantfysik, men endast effektivt för program med relativt få kvantbitar. Vi ser mycket fram emot att göra maskinvara för kvantberäkning tillgänglig som måldatorer i framtiden.
* *verktyg* för att arbeta med Q# så sömlöst som möjligt, till exempel tillägg för Visual Studio och VS Code och paket som ska användas med Python och Jupyter Notebooks.
* *API-dokumentation* för koppling av Q# med klassiska värdspråk som Python och C#

Program som har utvecklats med Microsofts Quantum Development Kit består vanligtvis av två delar:
1. En eller flera kvantalgoritmer som har implementerats med hjälp av kvantprogrammeringsspråket Q#, och anropats av det klassiska värdprogrammet. Det består av 
    - Q#-åtgärder: subrutiner som innehåller Quantum-åtgärder och 
    - Q#-funktioner: klassiska subrutiner som används inom Quantum-algoritmen.
2. Ett klassiskt program, som har implementerats i ett klassiskt programmeringsspråk som Python eller C#, som fungerar som huvudstartpunkt och som anropar Q#-åtgärder för att köra en kvantalgoritm.

## <a name="write-quantum-programs-not-quantum-circuits"></a>Skriv kvantprogram, inte kvantkretsar

I början när kvantberäkningsalgoritmerna visualiserades som diagram som liknade kretsdiagram i klassisk databehandling.
Även om kretsmodellen har varit användbar under många år vid kvantberäkning, tror vi på Microsoft att utvecklarna kan ta sig utanför kvantkretsarna och utveckla kvantalgoritmer och program med hjälp av Q#.
Q#-språket har skapats för att vi ska kunna dra nytta av vad vi lärt oss under årtionden av klassisk programvaruutveckling och ge kvantutvecklarna en språkfunktionalitet på hög nivå som inriktar sig på kvantberäkning.

## <a name="how-does-q-work"></a>Hur fungerar Q#?

Med programmeringsspråket Q# får du en intuitiv uppsättning typer, åtgärder och logiska uttryck när du ska utveckla algoritmer, utan att du behöver oroa dig för den interna logiken i kvantdatorn.

En av de grundläggande byggstenarna i Q# är `Qubit`-typen, som inte kan kopieras eller nås direkt, precis som en riktig kvantbit.
I stället kan vi mäta den och lagra resultatet av mätningen i en `Result`-variabel, som är en Q#-typ med två möjliga värden: `Zero` och `One`.
Konstruktioner som denna garanterar att algoritmerna alltid följer lagarna inom kvantfysik och kan köras utan problem på kvantdatorer eller i simulatorer.

Q# innehåller även klassiska logiska funktioner som villkor och loopar med vissa delar som ser till att alla kvantregler följs.
Du kan till exempel begränsa hur slingor körs för att säkerställa att kvantåtgärderna inte anropas inom funktioner som kanske bara innehåller deterministiska klassiska subrutiner.

Q#-program är ofta kopplade till ett värdprogram som skrivits C# i eller Python, vilket kan ge en bekväm organisation av klassisk kod och kvantkod.
Förutom stödet för språk som C# och Python, har QDK stöd för Jupyter Notebook med Jupyter-kärnan IQ#.

## <a name="what-can-i-use-q-for"></a>Vad kan jag använda Q# till?

### <a name="use-q-to-learn-quantum-computing"></a>Använda Q# för att lära sig kvantberäkning

Fram till nu var du tvungen att lära dig kretsmodellen när du skulle lära dig kvantberäkning, för att förstå algoritmernas format med sorterade sekvenser av kvantgrindar och mätningar. Med Q# kan du göra på ett annat sätt: Du kan lära dig kvantberäkning genom att skriva kvantprogram.

### <a name="use-q-to-design-quantum-algorithms"></a>Använda Q# till att utforma kvantalgoritmer

Med Q# får du ett växande antal bibliotek och användardefinierade typer som hjälper dig att implementera verktyg och skapa avancerade kvantalgoritmer. Behöver du t.ex. sammanfläta de två kvantbitarna q1 och q2? I stället för att använda de grindar som krävs separat för att hämta de sammanflätade kvantbitarna kan du använda den redan inbyggda åtgärden `PrepareEntangledState([q1], [q2])`.

### <a name="use-q-to-estimate-quantum-resources"></a>Beräkna kvantresurser med hjälp av Q#

Du kan simulera körningen av ditt Q#-program med kvantsimulatorn för tillstånd som medföljer Quantum Development Kit (QDK).  QDK innehåller också resursberäknare som ger dig insikter om prestandan för Q#-program som är för stora för att kunna köras på en simulator.  Detta är mycket värdefullt för algoritmkonstruktörer, eftersom de kan justera sina program till att använda färre resurser (t.ex. att färre kvantbitar körs i färre åtgärder) så att de kan köras på en kvantdator i mindre skala.

### <a name="use-q-to-validate-hardware-performance"></a>Använda Q# till att validera maskinvaruprestanda

Fördelen med att använda Q# är att ett program kan skrivas en gång och köras på kvantsimulatorer för felsökning och sedan köras på olika kvantdatorer.  Benchmark-program som skrivits i Q# kan köras för att validera maskinvaruprestanda och jämföra resultat, när kvantdatorer utvecklas och nya kvantdatorer blir tillgängliga.  

## <a name="next-steps"></a>Nästa steg

* [Hur kan jag lära mig om kvantberäkning?](xref:microsoft.quantum.overview.learn)
* [Kom igång med Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
