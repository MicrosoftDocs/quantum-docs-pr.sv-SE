---
title: Bidra till Quantum Development Kit | Microsoft Docs
description: Bidra till Quantum Development Kit
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
ms.openlocfilehash: 4be86c5045ece62ae3af40090a2cd344d965e65f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73057391"
---
# <a name="contributing-to-the-quantum-development-kit"></a>Bidra till Quantum Development Kit #

Quantum Development Kit är mer än en samling av verktyg för att skriva kvantprogram.
Det ingår i en stor community av personer som har upptäckt kvantberäkning, som forskar i kvantalgoritmer, som utvecklar nya program för kvantenheter och som på andra sätt arbetar för att få ut det mesta av kvantprogrammeringen.
Som medlem i communityn kan Quantum Development Kit erbjuda kvantutvecklare med olika bakgrunder de funktioner som de behöver.
Dina bidrag till Quantum Development Kit hjälper till att uppnå det målet genom att förbättra de verktyg som används av andra kvantutvecklare, hur dessa verktyg dokumenteras och även genom att skapa nya funktioner som gör hela kvantprogrammeringens community till en bättre plats där man kan upptäcka och skapa.
Vi är tacksamma för dina bidrag och för möjligheten att arbeta tillsammans med dig för att göra vår community till den allra bästa.

I den här guiden ger vi några tips på hur du gör ditt bidrag så användbart som möjligt för den bredare communityn inom kvantprogrammering.

## <a name="building-community"></a>Skapa en community ##

Det första du ska tänka på när du lämnar ett bidrag är att alltid komma ihåg vilken community du bidrar till.
Genom att agera respektfullt och professionellt mot dina kolleger i communityn för kvantprogrammering, hjälper du till att säkerställa att dina insatser skapar den bästa och mest välkomnande communityn.

Som en del av detta har alla Quantum Development Kit-projekt infört [Microsofts regler för uppförande i öppen källkod](https://opensource.microsoft.com/codeofconduct/).
Läs [Vanliga frågor och svar om regler för uppförande](https://opensource.microsoft.com/codeofconduct/faq/) eller kontakta [opencode@microsoft.com](mailto:opencode@microsoft.com) om du har några andra frågor eller kommentarer.

## <a name="what-kinds-of-contributions-help-the-community"></a>Vilka typer av bidrag kan vara till hjälp för communityn? ##

Det finns många olika sätt som du kan hjälpa communityn för kvantprogrammering med dina bidrag.
I den här guiden fokuserar vi på tre sätt som är särskilt relevanta för Quantum Development Kit.
Alla dessa sätt är viktiga för att skapa en kvantcommunity som hjälper andra människor.
Detta är definitivt inte en fullständig lista – vi rekommenderar att du utforskar även andra sätt för att hjälpa communityn att utveckla kvantprogrammering!

- **Rapportera buggar.** Det första steget i att åtgärda buggar och andra typer av problem är att identifiera dem. Om du berättar för oss att du har hittat en bugg i Quantum Development Kit hjälper du oss att åtgärda felet och göra uppsättningen med verktyg för kvantprogrammeringscommunityn ännu bättre.
- **Förbättra dokumentationen.** All dokumentation kan alltid bli bättre, ge mer information eller bli mer tillgänglig.
- **Bidra med kod.** Ett av de mest direkta sätten att bidra är naturligtvis att lägga till ny kod i Quantum Development Kit.

De olika typerna av bidrag är alla oerhört värdefulla och uppskattas mycket.
I resten av guiden ger vi råd om hur du skapar de olika typerna av bidrag.

## <a name="where-do-contributions-go"></a>Vart tar bidragen vägen? ##

Quantum Development Kit innehåller ett flertal olika delar som används tillsammans för att skapa en plattform där kvantprogram kan skrivas.
Var och en av dessa delar finns på en särskild lagringsplats, så en av de första sakerna du gör är att bestämma på vilken plats varje bidrag ska finnas.

- [**microsoft/Quantum**](https://github.com/Microsoft/Quantum): Exempel och verktyg som hjälper dig att komma igång med Quantum Development Kit.
- [**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries): Standardbibliotek och domänspecifika bibliotek för Quantum Development Kit.
- [**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas): Programmeringsövningar i egen takt för att lära sig kvantberäkning och programmeringsspråket Q#.
- [**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler): Q#-kompilerare, Visual Studio-tillägg och Visual Studio Code-tillägg.
- [**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime): Ramverk för simulering, kodgenerering och måldatorer till simulering för Quantum Development Kit.
- [**microsoft/iqsharp**](https://github.com/microsoft/iqsharp): Q#-funktioner för Jupyter-kernel och Python-värd, samt Docker-avbildningar för användning av IQ# i molnmiljöer.
- [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr): Källkoden för den dokumentation som publicerats på https://docs.microsoft.com/quantum.

> [!NOTE]
> Vi kan tyvärr inte acceptera kod- och dokumentationsbidrag på lagringsplatsen [**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC) just nu, men vi tar gärna emot felrapporter.

Det finns också några andra mer specialiserade lagringsplatser som fokuserar på olika händelser eller på extra funktioner som är relaterade till Quantum Development Kit.

- [**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty): Stöd för LaTeX-formatering av Q#-syntax.
- [**msr-quarc/intern-workshop-2019**](https://github.com/msr-quarc/intern-workshop-2019): IQ# Notebook for Deutsch–Jozsas självstudie från en intern workshop 2019.

## <a name="next-steps"></a>Nästa steg ##

Tack för att du är en del av communityn för Quantum Development Kit, vi är glada över dina bidrag!
Om du vill lära dig mer om att bidra, kan du fortsätta med någon av följande guider.

> [!div class="nextstepaction"]
> [Lär dig att rapportera buggar](xref:microsoft.quantum.contributing.reporting)

> [!div class="nextstepaction"]
> [Lär dig att bidra med dokumentation](xref:microsoft.quantum.contributing.docs)

> [!div class="nextstepaction"]
> [Lär dig att öppna pull-begäranden](xref:microsoft.quantum.contributing.pulls)
