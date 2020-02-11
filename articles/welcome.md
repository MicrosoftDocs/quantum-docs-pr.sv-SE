---
uid: microsoft.quantum.welcome
title: Kom igång med Quantum Development Kit (QDK)
description: Lär dig hur du kommer igång med QDK.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: overview
ms.openlocfilehash: 066981e3e2fb468c1ff2a4cf4d3e7cff057772ab
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036346"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Kom igång med Quantum Development Kit (QDK)

Välkommen till Microsoft Quantum Development Kit!  
QDK innehåller alla verktyg du behöver för att bygga egna kvantprogram och experiment med Q#, ett programmeringsspråk som utformats särskilt för kvantprogramutveckling. 

För att komma igång direkt kan du gå till [installationsguiden för QDK](xref:microsoft.quantum.install).
Du vägleds sedan genom installationen av Quantum Development Kit på Windows-, Linux- eller MacOS-datorer så att du kan skriva egna kvantprogram.

Om du inte är redo att börja koda men vill lära dig mer om kvantdatabehandling och Q# rekommenderar vi ändå att du läser den här artikeln för att få en överblick av de resurser du har tillgång till. I avsnittet [fem frågor om kvantberäkning](#five-questions-about-quantum-computing) hittar du länkar till exakt det du letar efter!

## <a name="get-started-programming"></a>Kom igång med programmering

I Quantum Development Kit finns det många sätt att lära sig att utveckla ett kvantprogram med Q#.
För att komma igång med kraften hos kvantberäkning kan du prova våra *snabbstarter*:

* [Slumptalsgeneratorn för kvanttal](xref:microsoft.quantum.quickstarts.qrng) är ett program i ”Q# Hello World”-format som ger en kort introduktion till kvantbegrepp där du kan skapa och köra ett kvantprogram på bara några minuter.
* [Kvantgrunder med Q#](xref:microsoft.quantum.write-program) hjälper dig att skriva ett Q#-program med några grundläggande begrepp inom kvantprogrammering. 
    Om du inte är redo att börja koda kan du ändå följa med utan att installera QD. Du får då en översikt över Q#-programmeringsspråket och de första begreppen inom kvantberäkning.
* [Grovers sökalgoritm](xref:microsoft.quantum.quickstarts.search) ger ett exempel på ett Q#-program som visar hur Q# kan uttrycka kvantalgoritmen på ett sätt som beskriver kvantåtgärder på en enkel nivå. 
    Den här snabbstarten visar hur du utvecklar programmet i olika programmeringsmiljöer (med en Python-värd eller med en .NET-språkvärd samt med Visual Studio eller Visual Studio Code).

### <a name="learning-further"></a>Lär dig ännu mer
* Om du vill gå in djupare på Q#-programmering kan du titta närmare på [Quantum Katas](https://github.com/Microsoft/QuantumKatas) – en samling med programmeringsövningar som du utför i egen takt och som ger dig en introduktion till kvantberäkning via programmeringsövningar i Q#.
    Många av dessa kata är även tillgängliga som Q#-notebooks. 
* På vår [lagringsplats med exempel](https://github.com/Microsoft/Quantum) demonstreras flera exempel på hur du skriver kvantprogram med hjälp av Q#. De flesta av dessa exempel är skrivna med våra [kvantbibliotek](https://github.com/Microsoft/QuantumLibraries) med öppen källkod, däribland biblioteken [standard](xref:microsoft.quantum.libraries.standard.intro) och [kemi](xref:microsoft.quantum.chemistry.concepts.intro) (mer information om dessa finns nedan).

## <a name="five-questions-about-quantum-computing"></a>Fem frågor om kvantberäkning

Om kvantutveckling är nytt för dig vet vi att det här ämnet kan verka svårt. Vi har tillhandahållit resurser som hjälper dig att komma igång med att lära dig om kvantberäkning. Vi är säkra på att du med hjälp av de här korta artiklarna snabbt kommer igång med programmeringen.
* [Vad är kvantberäkning?](xref:microsoft.quantum.overview.what)
* [Vad kan kvantdatorer göra?](xref:microsoft.quantum.overview.computers)
* [Varför ska man lära sig kvantberäkning?](xref:microsoft.quantum.overview.why)
* [Vad är Q#?](xref:microsoft.quantum.overview.qsharp)
* [Hur man lär sig kvantberäkning med Q#](xref:microsoft.quantum.overview.learn)

## <a name="quantum-development-kit-documentation"></a>Dokumentation för Quantum Development Kit

Den aktuella dokumentationen innehåller följande ytterligare ämnen.

### <a name="using-q"></a>Använda Q#
* [Tekniker för kvantutveckling](xref:microsoft.quantum.techniques.intro) beskriver de viktigaste begreppen som används för att skapa kvantprogram i Q#. Ämnena omfattar filstrukturer, operationer och funktioner, arbete med qubitar och vissa avancerade ämnen.
* [Q#-språkreferensen](xref:microsoft.quantum.language.intro) beskriver språket Q#, inklusive typmodellen, uttryck, instruktioner och kompilatoranvändning.
* [Kvantsimulatorer och värdprogram](xref:microsoft.quantum.machines) beskriver hur kvantalgoritmer körs, vilka kvantdatorer som är tillgängliga samt hur man skriver en icke-Q#-drivrutin för kvantprogrammet.

### <a name="q-libraries"></a>Q#-bibliotek
* [Q#-standardbiblioteket](xref:microsoft.quantum.libraries.standard.intro) beskriver de operationer och funktioner som stöder både det klassiska språkkontrollkravet och Q#-kvantalgoritmerna. 
    Avsnitten omfattar kontrollflöde, datastrukturer, felkorrigering, testning och felsökning. 
* [Q#-kemibiblioteket](xref:microsoft.quantum.chemistry.concepts.intro) beskriver de operationer och funktioner som stöder kvantkemisimulering – en viktig tillämpning av kvantberäkning. Ämnena omfattar simulering av hamiltonsk mekanik, kvantfasberäkning och mer.
* [Q#-nummerbiblioteket](xref:microsoft.quantum.numerics.intro) beskriver de operationer och funktioner som stöder uttryck av komplicerade aritmetiska funktioner i termer som gäller för måldatorernas inbyggda operationer.
* [Q#-biblioteksreferensen](xref:microsoft.quantum.standardlibsintro) innehåller referensinformation om biblioteksentiteter efter namnområde.

### <a name="general-quantum-computing"></a>Allmän kvantberäkning
* [Begrepp inom kvantberäkning](xref:microsoft.quantum.concepts.intro) innehåller ämnen såsom relevansen av linjär algebra för kvantberäkning, vad en qubit är och hur den används, hur du läser en kvantkrets och mer.
* [Ordlista för kvantberäkning](xref:microsoft.quantum.glossary) är en ordlista med några viktiga termer som gäller särskilt för kvantberäkning och programutveckling. 
    Om det här området är nytt för dig kan detta vara en praktisk referens när du läser igenom vår dokumentation.
* [Ytterligare läsning](xref:microsoft.quantum.more-information) innehåller särskilt valda referenser för djupgående information om ämnen som rör kvantberäkning.

### <a name="additional-info"></a>Ytterligare info
* [Viktig information för Microsoft Quantum Development Kit](xref:microsoft.quantum.relnotes).


## <a name="be-a-part-of-the-q-open-source-community"></a>Gå med i communityn för Q# med öppen källkod
Quantum Development Kit är ett utvecklingspaket med öppen källkod som gör det möjligt för utvecklare att göra kvantberäkning mer lättillgängligt för alla, så att vi kan lösa några av världens mest aktuella utmaningar.  Akademiska institutioner som behöver programvara med öppen källkod kommer att kunna distribuera Q# för sina utbildningar och sin utveckling inom kvantteknik. Tack vare att källkoden för utvecklingspaketet är öppen har utvecklare och domänexperter möjligheten att bidra med förbättringar och idéer via egen kod.

Din feedback, ditt deltagande och dina bidrag till Quantum Development Kit är viktiga.  Om du vill veta mer om Quantum Development Kit-källorna, ge feedback och ta reda på hur du kan delta i besluten samt bidra till den här växande kvantutvecklingsplattformen kan du läsa [Bidra till Quantum Development Kit](xref:microsoft.quantum.contributing).

Om du vill ha mer allmän information om Microsofts initiativ för kvantberäkning kan du läsa [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).
