---
title: Vad är Q#?
description: Lär dig mer om Q#, ett programmeringsspråk som skapats av Microsoft för att kunna utveckla program för kvantdatorer
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: 3fd288439c7db7f939240b4388c9cdb114b6535c
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529976"
---
# <a name="what-is-q"></a>Vad är Q#?

Q# är ett programmeringsspråk med funktioner som är specifika vid kvantberäkning.

Q# ger kvantprogrammerare ett ramverk som gör att de kan fokusera på algoritmerna utan att behöva tänka på teknisk information, till exempel optimering av grindar eller den fysiska implementeringen av en kvantdator.

Med programmeringsspråket Q# får du en intuitiv uppsättning typer, åtgärder och logiska uttryck när du ska utveckla algoritmer, utan att du behöver oroa dig för den interna logiken i kvantdatorn.

## <a name="code-algorithms"></a>Kodalgoritmer

I början när kvantberäkningsalgoritmerna visualiserades som diagram som liknade kretsdiagram i klassisk databehandling.  Även om kretsmodellen har varit användbar under många år vid kvantberäkning, tror vi på Microsoft att utvecklarna kan ta sig utanför kvantkretsarna och utveckla kvantalgoritmer och program med hjälp av Q#. Q#-språket har skapats för att vi ska kunna dra nytta av vad vi lärt oss under årtionden av klassisk programvaruutveckling och ge kvantutvecklarna en språkfunktionalitet på hög nivå som inriktar sig på kvantberäkning.


## <a name="how-does-q-work"></a>Hur fungerar Q#?

En av de grundläggande byggstenarna i Q# är `Qubit`-typen, som inte kan kopieras eller nås direkt, precis som en riktig kvantbit. I stället kan vi mäta den och lagra resultatet av mätningen i en `Result`-variabel, som är en Q#-typ med två möjliga värden: `Zero` och `One`. Konstruktioner som denna garanterar att algoritmerna alltid följer lagarna inom kvantfysik och kan köras utan problem på kvantdatorer eller i simulatorer.

Q# innehåller även klassiska logiska funktioner som villkor eller loopar med vissa delar som ser till att alla kvantregler följs. Du kan till exempel begränsa hur slingor körs för att säkerställa kvantåtgärderna.

Q#-program är ofta kopplade till ett värdprogram som skrivits C# i eller Python, vilket kan ge en bekväm organisation av klassisk kod och kvantkod. Förutom stödet för språk som C# och Python, har QDK stöd för Jupyter Notebook med Jupyter-kärnan IQ#.

## <a name="use-q-to-learn-quantum-computing"></a>Använda Q# för att lära sig kvantberäkning

Fram till nu var du tvungen att lära dig kretsmodellen när du skulle lära dig kvantberäkning, för att förstå algoritmernas format med sorterade sekvenser av kvantgrindar och mätningar. Med Q# kan du göra på ett annat sätt: Du kan lära dig kvantberäkning genom att skriva kvantprogram.

## <a name="use-q-to-design-quantum-algorithms"></a>Använda Q# till att utforma kvantalgoritmer

Med Q# får du ett växande antal bibliotek och användardefinierade typer som hjälper dig att implementera verktyg och skapa avancerade kvantalgoritmer. Behöver du t.ex. sammanfläta de två kvantbitarna q1 och q2? I stället för att använda de grindar som krävs separat för att hämta de sammanflätade kvantbitarna kan du använda den redan inbyggda åtgärden `PrepareEntangledState([q1], [q2])`.

## <a name="use-q-to-estimate-quantum-resources"></a>Beräkna kvantresurser med hjälp av Q#

Du kan simulera körningen av ditt Q#-program med kvantsimulatorn för tillstånd som medföljer Quantum Development Kit (QDK).  QDK innehåller också resursberäknare som ger dig insikter om prestandan för Q#-program som är för stora för att kunna köras på en simulator.  Detta är mycket värdefullt för algoritmkonstruktörer, eftersom de kan justera sina program till att använda färre resurser (t.ex. att färre kvantbitar körs i färre åtgärder) så att de kan köras på en kvantdator i mindre skala.

## <a name="use-q-to-validate-hardware-performance"></a>Använda Q# till att validera maskinvaruprestanda

Fördelen med att använda Q# är att ett program kan skrivas en gång och köras på kvantsimulatorer för felsökning och sedan köras på olika kvantdatorer.  Benchmark-program som skrivits i Q# kan köras för att validera maskinvaruprestanda och jämföra resultat, när kvantdatorer utvecklas och nya kvantdatorer blir tillgängliga.  

## <a name="next-steps"></a>Nästa steg

* [Hur lär jag mig kvantberäkning?](xref:microsoft.quantum.overview.learn)
* [Kom igång med Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
