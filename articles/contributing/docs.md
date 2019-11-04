---
title: Dokumentation om bidrag | Microsoft Docs
description: Bidrags dokumentation
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: 1e24dd859c0b75a161f4f3c7151e2eec227075a2
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183683"
---
# <a name="improving-documentation"></a>Förbättra dokumentation #

Dokumentationen för Quantum Development Kit tar flera olika formulär, så att informationen är lätt att komma åt i Quantum-utvecklare.

Enligt principerna för dokumentation [som kod](https://www.writethedocs.org/guide/docs-as-code/)är all Quantum Development Kit-dokumentationen formaterad som kod och hanteras med git på samma sätt som käll koden som används för att bygga quantum Development Kit.
Den kod som används för att säkerhetskopiera dokument består av olika former av [markdown](https://daringfireball.net/projects/markdown/), ett språk för att skriva formaterad text i ett oformaterat text format som är enkelt att använda på kommando raden, i IDE: er och med käll kontroll.
Vi antar ungefär [MathJax](https://www.mathjax.org/) -biblioteket för att kunna formatera matematik i dokumentation med latex-språket, som beskrivs nedan.


Detta innebär att varje form av dokumentation varierar något i detaljerna:

- Den **konceptuella dokumentationen** består av en uppsättning artiklar som publiceras till https://docs.microsoft.com/quantum och som beskriver allt från grunderna i Quantum Computing till de tekniska specifikationerna för Interchange Format. De här artiklarna är skrivna i [DocFX-markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), en markdown-variant som används för att skapa rika dokumentations uppsättningar.
- **API-referensen** är en uppsättning sidor för varje Q #-funktion,-åtgärd och användardefinierad typ, publicerad till https://docs.microsoft.com/qsharp/api/. Dessa sidor dokumenterar indata och åtgärder för varje anrop, tillsammans med exempel och länkar till mer information. API-referensen extraheras automatiskt från små DFM-dokument i Q # käll kod som en del av varje version.
- README-filerna **<!---->. MD** som ingår i varje exempel och Kata beskriver hur du använder det här exemplet eller Kata, vad det täcker och hur det är relaterat till resten av Quantum Development Kit. De här filerna skrivs med [GitHub-markdown (GFM)](https://github.github.com/gfm/), ett mer lätt alternativ till DFM som är populärt för att bifoga dokumentation direkt till kod centraler.

## <a name="contributing-to-the-conceptual-documentation"></a>Bidra till den konceptuella dokumentationen ##

För att bidra till en förbättring av den konceptuella dokumentationen eller README-dokumentationen börjar du med en pull-begäran till antingen [**Microsoft docs/Quantum-dok-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)eller [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), vilket är lämpligt.
Vi beskriver mer om pull-begäranden nedan, men för närvarande finns det några saker som du bör tänka på när du förbättrar dokumentationen:

- Läsarna kommer till dokumentationen för Quantum Development Kit från en mängd olika bakgrunder. Alla från högskole studenter vill lära sig något nytt och spännande till förbrukade lärare som utför data behandling med Quantum Computing, ska kunna få något att läsa dokumentationen. I den utsträckning det är möjligt bör du inte ta med omfattande kunskaper om en del av läsarna, eftersom de bara kan starta. Det är mest användbart om du kan tillhandahålla tydliga och tillgängliga beskrivningar, eller också kan du ange länkar till andra resurser för mer information.
- Dokumentations uppsättningar som inte finns på samma sätt som böcker eller dokument, i de läsarna kommer att komma i det som kan verka som "mellan". Sökmotorer kan till exempel inte föreslå index, eller så kan de ha fått en länk med en vän som försöker hjälpa dem. Försök att hjälpa läsaren genom att alltid tillhandahålla en tydlig kontext, tillsammans med länkar där det är lämpligt.
- Vissa läsare kommer att hitta abstrakta instruktioner och definitioner som är mest användbara, medan andra läsare fungerar bäst genom att extrapolera från konkreta exempel. Att tillhandahålla både det allmänna fallet och vissa exempel kan hjälpa båda läsarna att få ut det mesta av Quantum-programmering.
- I synnerhet om du också skrev koden som dokumenteras kan det vara självklart att det är självklart att du inte är helt uppenbart för läsaren. Det finns ingen unik metod för program, så oavsett hur smarta eller erfarna en läsare kan vara kan de inte gissa sig till vilka design mönster du har visat mest användbara för att uttrycka dina idéer i kod. Att ta bort om hur en läsare kan förväntar sig att använda koden kan hjälpa till att tillhandahålla den kontexten.
- Många medlemmar i Quantum Programming community är akademiska forskare, och erkänns huvudsakligen genom citat från sina bidrag till communityn. Förutom att hjälpa läsarna att hitta ytterligare material, och se till att korrekt citera akademiska utdata, till exempel papper, samtal, blogg inlägg och program varu verktyg, kan hjälpa akademiska deltagare att utföra sitt bästa arbete för att förbättra samhället.
- Quantum Programming community är en bred och mycket bred grupp. Användning av köns prosubstantiv i exempel på tredje person (t. ex.: "om en användare...") kan användas för att utesluta i stället för att inkludera. Att vara cognizant av personens namn i Citats och länkar, och rätt inkludering av icke-ASCII-tecken kan tjäna på mångfalden av communityn genom att visa respekt för dess medlemmar. På samma sätt används många ord på det engelska språket ofta på ett hatefult sätt, så att deras användning i den tekniska dokumentationen kan orsaka skada både enskilda läsare och till communityn i stor utsträckning.

## <a name="contributing-to-the-api-references"></a>Bidrag till API-referenser ##

För att bidra till en förbättring av API-referenserna är det mest användbart att öppna en pull-begäran direkt på den kod som dokumenteras.
Varje funktion, åtgärd eller användardefinierad typ har stöd för en dokumentations kommentar (betecknas med `///` i stället för `//`).
När vi kompilerar varje version av Quantum Development Kit, används dessa kommentarer för att generera API-referensen på https://docs.microsoft.com/qsharp/api/ , inklusive information om indata till och utdata från varje anrop, antaganden om varje anrops bara och exempel på hur de kan användas.

> [!IMPORTANT]
> Se till att du inte redigerar den genererade API-dokumentationen manuellt, eftersom filerna skrivs över med varje ny version.
> Vi använder oss av ditt bidrag till communityn och vill se till att ändringarna fortsätter att hjälpa användarna att lansera efter lanseringen.

Överväg till exempel en åtgärd `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`.
En dokumentations kommentar bör hjälpa en användare att lära sig hur man tolkar `angles`, vad som förutsätter att den ursprungliga statusen för `register`, vad som händer i `register` och så vidare.
Var och en av dessa olika informations delar kan ges till Q #-kompilatorn med ett särskilt namngivet markdown-avsnitt i dokumentations kommentaren.
I exemplet på `PrepareTrialState`kan vi skriva något som liknar följande:

```qsharp
/// # Summary
/// Given a register of qubits, prepares them in a trial state by rotating each
/// independently.
///
/// # Description
/// This operation prepares the input register by performing a
/// $Y$ rotation on each qubit by an angle given in `angles`.
///
/// # Input
/// ## angles
/// An array of parameters
/// ## register
/// A register of qubits initially in the $\ket{00\cdots0}$ state.
///
/// # Example
/// To prepare an equal superposition $\ket{++\cdots+}$ over all input qubits:
/// ```qsharp
/// PrepareTrialState(ConstantArray(Length(register), PI() / 2.0), register);
/// ```
///
/// # Remarks
/// This operation is generally useful in the inner loop of an optimization
/// algorithm.
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.Ry
operation PrepareTrialState(angles : Double[], register : Qubit[]) : Unit {
    // ...
}
```

Förutom den allmänna metoden för dokumentations skrivning, i skriva API-dokumentation kommentarer, hjälper det till att hålla några saker i åtanke:

- Formatet för varje dokumentations kommentar måste matcha vad Q #-kompilatorn förväntar sig att din dokumentation ska visas korrekt. Vissa avsnitt, till exempel `/// # Remarks` tillåter fri hands innehåll, medan avsnitt som `/// # See Also` avsnittet är mer restriktiva.
- En läsare kan läsa API-dokumentationen på huvud-API-referens webbplatsen, på sammanfattningen för varje namn område eller till och med i IDE genom att använda hov rings information. Se till att `/// # Summary` inte längre än om en mening hjälper läsaren att snabbt sortera om de behöver läsa mer eller titta någon annan stans, och kan hjälpa dig att snabbt söka igenom sammanfattningar av namn områden.
- Dokumentationen kan vara mycket längre än själva koden, men det är OK! Även en liten del av koden kan ha oväntade effekter för användare som inte känner till sammanhanget där koden finns. Genom att tillhandahålla konkreta exempel och tydliga förklaringar kan du hjälpa användarna att göra den bästa användningen av den kod som är tillgänglig för dem.

<!-- ## LaTeX Formatting ##

**TODO** -->
