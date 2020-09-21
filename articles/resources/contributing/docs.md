---
title: Bidra med dokumentation till Microsoft QDK
description: Lär dig att bidra med konceptuell eller API-innehåll till Microsoft Quantum-dokumentationen.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 20e9f8126a290f52701b6b0e525d7669a605d4c9
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759687"
---
# <a name="improving-documentation"></a>Förbättra dokumentationen

Dokumentationen för Quantum Development Kit tar flera olika formulär, så att informationen är lätt att komma åt i Quantum-utvecklare.

Enligt principerna för dokumentation [som kod](https://www.writethedocs.org/guide/docs-as-code/)är all Quantum Development Kit-dokumentationen formaterad som kod och hanteras med git på samma sätt som käll koden som används för att bygga quantum Development Kit.
Den kod som används för att säkerhetskopiera dokument består av olika former av [markdown](https://daringfireball.net/projects/markdown/), ett språk för att skriva formaterad text i ett oformaterat text format som är enkelt att använda på kommando raden, i IDE: er och med käll kontroll.
Vi antar ungefär [MathJax](https://www.mathjax.org/) -biblioteket för att kunna formatera matematik i dokumentation med latex-språket, som beskrivs nedan.


Detta innebär att varje form av dokumentation varierar något i detaljerna:

- Den **konceptuella dokumentationen** består av en uppsättning artiklar som publiceras till https://docs.microsoft.com/quantum och som beskriver allt från grunderna i Quantum Computing till de tekniska specifikationerna för Interchange Format. De här artiklarna är skrivna i [DocFX-markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), en markdown-variant som används för att skapa rika dokumentations uppsättningar.
- **API-referensen** är en uppsättning sidor för varje Q# funktion, åtgärd och användardefinierad typ, publicerad till https://docs.microsoft.com/qsharp/api/ . Dessa sidor dokumenterar indata och åtgärder för varje anrop, tillsammans med exempel och länkar till mer information. API-referensen extraheras automatiskt från små DFM dokument i Q# käll koden som en del av varje version.
- **README <!----> . MD** -filerna som ingår i varje exempel och Kata beskriver hur du använder det exemplet eller Kata används, vad det täcker och hur det är relaterat till resten av Quantum Development Kit. De här filerna skrivs med [GitHub-markdown (GFM)](https://github.github.com/gfm/), ett mer lätt alternativ till DFM som är populärt för att bifoga dokumentation direkt till kod centraler.

## <a name="contributing-to-the-conceptual-documentation"></a>Bidra till den konceptuella dokumentationen

För att bidra till en förbättring av den konceptuella dokumentationen eller README-dokumentationen börjar du med en pull-begäran till antingen [**Microsoft docs/Quantum-dok-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)eller [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), vilket är lämpligt.
Vi beskriver mer om pull-begäranden nedan, men för närvarande finns det några saker som du bör tänka på när du förbättrar dokumentationen:

- Läsarna kommer till dokumentationen för Quantum Development Kit från en mängd olika bakgrunder. Alla från högskole studenter vill lära sig något nytt och spännande till förbrukade lärare som utför data behandling med Quantum Computing, ska kunna få något att läsa dokumentationen. I den utsträckning det är möjligt bör du inte ta med omfattande kunskaper om en del av läsarna, eftersom de bara kan starta. Det är mest användbart om du kan tillhandahålla tydliga och tillgängliga beskrivningar, eller också kan du ange länkar till andra resurser för mer information.
- Dokumentations uppsättningar som inte finns på samma sätt som böcker eller dokument, i de läsarna kommer att komma i det som kan verka som "mellan". Sökmotorer kan till exempel inte föreslå index, eller så kan de ha fått en länk med en vän som försöker hjälpa dem. Försök att hjälpa läsaren genom att alltid tillhandahålla en tydlig kontext, tillsammans med länkar där det är lämpligt.
- Vissa läsare kommer att hitta abstrakta instruktioner och definitioner som är mest användbara, medan andra läsare fungerar bäst genom att extrapolera från konkreta exempel. Att tillhandahålla både det allmänna fallet och vissa exempel kan hjälpa båda läsarna att få ut det mesta av Quantum-programmering.
- I synnerhet om du också skrev koden som dokumenteras kan det vara självklart att det är självklart att du inte är helt uppenbart för läsaren. Det finns ingen unik metod för program, så oavsett hur smarta eller erfarna en läsare kan vara kan de inte gissa sig till vilka design mönster du har visat mest användbara för att uttrycka dina idéer i kod. Att ta bort om hur en läsare kan förväntar sig att använda koden kan hjälpa till att tillhandahålla den kontexten.
- Många medlemmar i Quantum Programming community är akademiska forskare, och erkänns huvudsakligen genom citat från sina bidrag till communityn. Förutom att hjälpa läsarna att hitta ytterligare material, och se till att korrekt citera akademiska utdata, till exempel papper, samtal, blogg inlägg och program varu verktyg, kan hjälpa akademiska deltagare att utföra sitt bästa arbete för att förbättra samhället.
- Quantum Programming community är en bred och mycket bred grupp. Användning av köns prosubstantiv i exempel på tredje person (t. ex.: "om en användare...") kan användas för att utesluta i stället för att inkludera. Att vara cognizant av personens namn i Citats och länkar, och rätt inkludering av icke-ASCII-tecken kan tjäna på mångfalden av communityn genom att visa respekt för dess medlemmar. På samma sätt används många ord på det engelska språket ofta på ett hatefult sätt, så att deras användning i den tekniska dokumentationen kan orsaka skada både enskilda läsare och till communityn i stor utsträckning.

### <a name="referencing-sample-code-from-conceptual-articles"></a>Referera till exempel kod från konceptuella artiklar

Om du vill inkludera kod från [exempel databasen](https://github.com/Microsoft/Quantum)kan du göra det med hjälp av ett särskilt DocFX markdown-kommando:

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

Det här kommandot importerar rader 4 till 8 av [ `Game.qs` filen från `chsh-game` exemplet](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs)och markerar dem som Q# kod för markering av syntax.
Med det här kommandot kan du undvika att duplicera kod mellan konceptuella artiklar och exempel databasen, så att exempel koden i dokumentationen alltid är så aktuell som möjligt.

## <a name="contributing-to-the-api-references"></a>Bidrag till API-referenser

För att bidra till en förbättring av API-referenserna är det mest användbart att öppna en pull-begäran direkt på den kod som dokumenteras.
Varje funktion, åtgärd eller användardefinierad typ har stöd för en dokumentations kommentar (anges i `///` stället för `//` ).
När vi kompilerar varje version av Quantum Development Kit, används dessa kommentarer för att generera API-referensen vid https://docs.microsoft.com/qsharp/api/ , inklusive information om indata till och utdata från varje anrops man, antaganden om varje anrops bara och exempel på hur de kan användas.

> [!IMPORTANT]
> Se till att du inte redigerar den genererade API-dokumentationen manuellt, eftersom filerna skrivs över med varje ny version.
> Vi använder oss av ditt bidrag till communityn och vill se till att ändringarna fortsätter att hjälpa användarna att lansera efter lanseringen.

Anta till exempel funktionen `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` .
En dokumentations kommentar bör hjälpa en användare att lära sig hur man tolkar `bits` och `oracle` och vad funktionen är för.
Var och en av dessa olika delar av information kan ges till Q# kompilatorn med ett särskilt namngivet markdown-avsnitt i dokumentations kommentaren.
Vi kan till exempel `ControlledOnBitString` skriva något som liknar följande:

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

Du kan se den återgivna versionen av koden ovan i API- [dokumentationen för `ControlledOnBitString` funktionen](xref:microsoft.quantum.canon.controlledonbitstring).

Förutom den allmänna metoden för dokumentations skrivning, i skriva API-dokumentation kommentarer, hjälper det till att hålla några saker i åtanke:

- Formatet för varje dokumentations kommentar måste matcha vad Q# kompileraren förväntar sig att din dokumentation ska visas korrekt. Vissa avsnitt, till exempel `/// # Remarks` för att tillåta fri hands innehåll, medan avsnitt som `/// # See Also` avsnittet är mer restriktiva.
- En läsare kan läsa API-dokumentationen på huvud-API-referens webbplatsen, på sammanfattningen för varje namn område eller till och med i IDE genom att använda hov rings information. Se till att det `/// # Summary` inte är längre än om en mening hjälper läsaren att snabbt sortera om de behöver läsa mer eller titta någon annan stans, och kan hjälpa till att snabbt söka igenom sammanfattningar av namn områden.
- Dokumentationen kan vara mycket längre än själva koden, men det är OK! Även en liten del av koden kan ha oväntade effekter för användare som inte känner till sammanhanget där koden finns. Genom att tillhandahålla konkreta exempel och tydliga förklaringar kan du hjälpa användarna att göra den bästa användningen av den kod som är tillgänglig för dem.

<!-- ## LaTeX Formatting ##

**TODO** -->
