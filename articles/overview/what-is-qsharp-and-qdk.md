---
title: Vad är programmeringsspråket Q# och QDK?
description: Lär dig mer om Microsoft Quantum Development Kit, programmeringsspråket Q# samt hur du kan skapa kvantprogram.
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5db574b0380ffa1616cb3959d84925854df4e321
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863781"
---
# <a name="what-are-the-no-locq-programming-language-and-qdk"></a>Vad är programmeringsspråket Q# och QDK?

Q# är Microsofts programmeringsspråk med öppen källkod för utveckling och körning av kvantalgoritmer. Det ingår i Quantum Development Kit (QDK), som innehåller [Q#-bibliotek](xref:microsoft.quantum.libraries), [kvantsimulatorer](xref:microsoft.quantum.machines), [tillägg för andra programmeringsmiljöer](xref:microsoft.quantum.install) och [API-dokumentation](xref:microsoft.quantum.standardlibsintro). Utöver standardbiblioteket för Q# innehåller QDK även biblioteken för kemi, maskininlärning och tal.

Som programmeringsspråk omfattar Q# välkända element från Python, C# och F#. Det stöder en grundläggande procedurmodell för skrivande av program med loopar, if/then-instruktioner och vanliga datatyper. Det introducerar även nya kvantspecifika datastrukturer och åtgärder.

## <a name="what-can-i-do-with-the-qdk"></a>Vad kan jag göra med QDK?

QDK är en komplett development kit för Q# som du kan använda med vanliga verktyg och språk för att utveckla kvantprogram som du kan köra i olika miljöer. Q#-program kan köras som ett konsolprogram, via Jupyter Notebooks eller med ett Python- eller .NET-värdprogram.

### <a name="develop-in-common-tools-and-environments"></a>Utveckla i vanliga verktyg och miljöer

Integrera din kvantutveckling med [Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone) och [Jupyter Notebooks](xref:microsoft.quantum.install.jupyter). Använd de inbyggda API:erna för att koppla ihop dina program med värdspråken [Python](xref:microsoft.quantum.install.python) och [.NET](xref:microsoft.quantum.install.cs).

### <a name="try-quantum-operations-and-domain-specific-libraries"></a>Prova kvantåtgärder och domänspecifika bibliotek

Skriv och testa kvantalgoritmer för att utforska superposition, sammanflätning och andra kvantåtgärder. Med Q#-biblioteken kan du köra komplexa kvantåtgärder utan att behöva utforma åtgärder på låg nivå.

### <a name="run-programs-in-simulators"></a>Köra program i simulatorer

Kör kvantprogram i en kvantsimulator med fullständigt tillstånd eller en Toffoli-simulator med begränsat omfång, eller testa Q#-kod i olika resursberäknare. 

## <a name="where-can-i-learn-more"></a>Var hittar jag mer information?

|||
| ---- | ---- |
| **Kvantberäkning är nytt för mig** | Gå igenom några grunder inom kvantfysik och kvantberäkning i [Viktiga begrepp](xref:microsoft.quantum.overview.understanding).|
| **Jag vill gå in närmare på språket Q#** | Utforska typer, uttryck, variabler och kvantprogramstrukturer i [användarhandboken för Q#](xref:microsoft.quantum.guide).|
| **Jag vill bara börja skriva kvantprogram** | Konfigurera din Q#-miljö och börja skriva kvantprogram i [Snabbstarter](xref:microsoft.quantum.install).|

## <a name="how-does-no-locq-work"></a>Hur fungerar Q#?

Q#-program kan kompileras till ett fristående program eller anropas av ett värdprogram som är skrivet i antingen Python eller ett .NET-språk.

När du kompilerar och kör programmet skapar det en instans av kvantsimulatorn och skickar Q#-koden till den. Simulatorn använder Q#-koden för att skapa kvantbitar (simuleringar av kvantpartiklar) och tillämpa transformeringar för att ändra deras tillstånd. Resultatet av kvantåtgärderna i simulatorn returneras sedan till programmet.  

Isolering av Q#-koden i simulatorn ser till att algoritmerna följer kvantfysikens lagar och att de körs korrekt på kvantdatorer.

![qsharp-code-flow](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a>Hur använder jag QDK?

Allt du behöver för att skriva och köra Q#-program, inklusive Q#-kompilatorn, Q#-bibliotek och kvantsimulatorerna, kan installeras och köras från din lokala dator. Så småningom kan du köra Q#-programmen via fjärranslutning på en riktig kvantdator, men till dess tillhandahåller de kvantsimulatorer som medföljer QDK noggranna och tillförlitliga resultat.

- Att utveckla [Q#-program](xref:microsoft.quantum.install.standalone) är det snabbaste sättet att komma igång.

- Kör fristående [Jupyter Notebooks med IQ#](xref:microsoft.quantum.install.jupyter), ett Jupyter-tillägg för kompilering, simulering och visualisering av Q#-program.

- Om du är bekant med [Python](xref:microsoft.quantum.install.python) kan du använda det som en värdprogrammeringsplattform för att komma igång. Python är populärt både bland både utvecklare, forskare och lärare.

- Om du redan har erfarenhet av [C#, F# eller VB.NET](xref:microsoft.quantum.install.cs) och är bekant med utvecklingsmiljön i Visual Studio behöver du bara lägga till några tillägg i Visual Studio för att förbereda det för Q#.  

## <a name="summary"></a>Sammanfattning

Q# är ett programmeringsspråk med öppen källkod för utveckling av kvantprogram. Det innehåller bibliotek som du kan använda för att skapa komplexa kvantåtgärder samt kvantsimulatorer där du kan köra och testa dina program med korrekta resultat. Q#-program kan köras som fristående appar eller anropas från ett Python- eller .NET-värdprogram, och de kan skrivas, köras och testas från din lokala dator.

## <a name="next-steps"></a>Efterföljande moment

[Linjär algebra för kvantberäkning](xref:microsoft.quantum.overview.algebra)
