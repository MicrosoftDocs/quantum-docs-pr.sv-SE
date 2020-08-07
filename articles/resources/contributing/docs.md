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
ms.openlocfilehash: 1110f32a6486de1a346b115fa928a098749b6690
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866884"
---
# <a name="improving-documentation"></a><span data-ttu-id="451e6-103">Förbättra dokumentationen</span><span class="sxs-lookup"><span data-stu-id="451e6-103">Improving Documentation</span></span>

<span data-ttu-id="451e6-104">Dokumentationen för Quantum Development Kit tar flera olika formulär, så att informationen är lätt att komma åt i Quantum-utvecklare.</span><span class="sxs-lookup"><span data-stu-id="451e6-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="451e6-105">Enligt principerna för dokumentation [som kod](https://www.writethedocs.org/guide/docs-as-code/)är all Quantum Development Kit-dokumentationen formaterad som kod och hanteras med git på samma sätt som käll koden som används för att bygga quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="451e6-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="451e6-106">Den kod som används för att säkerhetskopiera dokument består av olika former av [markdown](https://daringfireball.net/projects/markdown/), ett språk för att skriva formaterad text i ett oformaterat text format som är enkelt att använda på kommando raden, i IDE: er och med käll kontroll.</span><span class="sxs-lookup"><span data-stu-id="451e6-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="451e6-107">Vi antar ungefär [MathJax](https://www.mathjax.org/) -biblioteket för att kunna formatera matematik i dokumentation med latex-språket, som beskrivs nedan.</span><span class="sxs-lookup"><span data-stu-id="451e6-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="451e6-108">Detta innebär att varje form av dokumentation varierar något i detaljerna:</span><span class="sxs-lookup"><span data-stu-id="451e6-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="451e6-109">Den **konceptuella dokumentationen** består av en uppsättning artiklar som publiceras till https://docs.microsoft.com/quantum och som beskriver allt från grunderna i Quantum Computing till de tekniska specifikationerna för Interchange Format.</span><span class="sxs-lookup"><span data-stu-id="451e6-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="451e6-110">De här artiklarna är skrivna i [DocFX-markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), en markdown-variant som används för att skapa rika dokumentations uppsättningar.</span><span class="sxs-lookup"><span data-stu-id="451e6-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="451e6-111">**API-referensen** är en uppsättning sidor för varje Q# funktion, åtgärd och användardefinierad typ, publicerad till https://docs.microsoft.com/qsharp/api/ .</span><span class="sxs-lookup"><span data-stu-id="451e6-111">The **API reference** is a set of pages for each Q# function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="451e6-112">Dessa sidor dokumenterar indata och åtgärder för varje anrop, tillsammans med exempel och länkar till mer information.</span><span class="sxs-lookup"><span data-stu-id="451e6-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="451e6-113">API-referensen extraheras automatiskt från små DFM dokument i Q# käll koden som en del av varje version.</span><span class="sxs-lookup"><span data-stu-id="451e6-113">The API reference is automatically extracted from small DFM documents in Q# source code as a part of each release.</span></span>
- <span data-ttu-id="451e6-114">**README <!----> . MD** -filerna som ingår i varje exempel och Kata beskriver hur du använder det exemplet eller Kata används, vad det täcker och hur det är relaterat till resten av Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="451e6-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="451e6-115">De här filerna skrivs med [GitHub-markdown (GFM)](https://github.github.com/gfm/), ett mer lätt alternativ till DFM som är populärt för att bifoga dokumentation direkt till kod centraler.</span><span class="sxs-lookup"><span data-stu-id="451e6-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="451e6-116">Bidra till den konceptuella dokumentationen</span><span class="sxs-lookup"><span data-stu-id="451e6-116">Contributing to the Conceptual Documentation</span></span>

<span data-ttu-id="451e6-117">För att bidra till en förbättring av den konceptuella dokumentationen eller README-dokumentationen börjar du med en pull-begäran till antingen [**Microsoft docs/Quantum-dok-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)eller [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), vilket är lämpligt.</span><span class="sxs-lookup"><span data-stu-id="451e6-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="451e6-118">Vi beskriver mer om pull-begäranden nedan, men för närvarande finns det några saker som du bör tänka på när du förbättrar dokumentationen:</span><span class="sxs-lookup"><span data-stu-id="451e6-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="451e6-119">Läsarna kommer till dokumentationen för Quantum Development Kit från en mängd olika bakgrunder.</span><span class="sxs-lookup"><span data-stu-id="451e6-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="451e6-120">Alla från högskole studenter vill lära sig något nytt och spännande till förbrukade lärare som utför data behandling med Quantum Computing, ska kunna få något att läsa dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="451e6-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="451e6-121">I den utsträckning det är möjligt bör du inte ta med omfattande kunskaper om en del av läsarna, eftersom de bara kan starta. Det är mest användbart om du kan tillhandahålla tydliga och tillgängliga beskrivningar, eller också kan du ange länkar till andra resurser för mer information.</span><span class="sxs-lookup"><span data-stu-id="451e6-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="451e6-122">Dokumentations uppsättningar som inte finns på samma sätt som böcker eller dokument, i de läsarna kommer att komma i det som kan verka som "mellan".</span><span class="sxs-lookup"><span data-stu-id="451e6-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="451e6-123">Sökmotorer kan till exempel inte föreslå index, eller så kan de ha fått en länk med en vän som försöker hjälpa dem. Försök att hjälpa läsaren genom att alltid tillhandahålla en tydlig kontext, tillsammans med länkar där det är lämpligt.</span><span class="sxs-lookup"><span data-stu-id="451e6-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="451e6-124">Vissa läsare kommer att hitta abstrakta instruktioner och definitioner som är mest användbara, medan andra läsare fungerar bäst genom att extrapolera från konkreta exempel.</span><span class="sxs-lookup"><span data-stu-id="451e6-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="451e6-125">Att tillhandahålla både det allmänna fallet och vissa exempel kan hjälpa båda läsarna att få ut det mesta av Quantum-programmering.</span><span class="sxs-lookup"><span data-stu-id="451e6-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="451e6-126">I synnerhet om du också skrev koden som dokumenteras kan det vara självklart att det är självklart att du inte är helt uppenbart för läsaren.</span><span class="sxs-lookup"><span data-stu-id="451e6-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="451e6-127">Det finns ingen unik metod för program, så oavsett hur smarta eller erfarna en läsare kan vara kan de inte gissa sig till vilka design mönster du har visat mest användbara för att uttrycka dina idéer i kod.</span><span class="sxs-lookup"><span data-stu-id="451e6-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="451e6-128">Att ta bort om hur en läsare kan förväntar sig att använda koden kan hjälpa till att tillhandahålla den kontexten.</span><span class="sxs-lookup"><span data-stu-id="451e6-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="451e6-129">Många medlemmar i Quantum Programming community är akademiska forskare, och erkänns huvudsakligen genom citat från sina bidrag till communityn.</span><span class="sxs-lookup"><span data-stu-id="451e6-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="451e6-130">Förutom att hjälpa läsarna att hitta ytterligare material, och se till att korrekt citera akademiska utdata, till exempel papper, samtal, blogg inlägg och program varu verktyg, kan hjälpa akademiska deltagare att utföra sitt bästa arbete för att förbättra samhället.</span><span class="sxs-lookup"><span data-stu-id="451e6-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="451e6-131">Quantum Programming community är en bred och mycket bred grupp.</span><span class="sxs-lookup"><span data-stu-id="451e6-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="451e6-132">Användning av köns prosubstantiv i exempel på tredje person (t. ex.: "om en användare...") kan användas för att utesluta i stället för att inkludera.</span><span class="sxs-lookup"><span data-stu-id="451e6-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., he will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="451e6-133">Att vara cognizant av personens namn i Citats och länkar, och rätt inkludering av icke-ASCII-tecken kan tjäna på mångfalden av communityn genom att visa respekt för dess medlemmar.</span><span class="sxs-lookup"><span data-stu-id="451e6-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="451e6-134">På samma sätt används många ord på det engelska språket ofta på ett hatefult sätt, så att deras användning i den tekniska dokumentationen kan orsaka skada både enskilda läsare och till communityn i stor utsträckning.</span><span class="sxs-lookup"><span data-stu-id="451e6-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

### <a name="referencing-sample-code-from-conceptual-articles"></a><span data-ttu-id="451e6-135">Referera till exempel kod från konceptuella artiklar</span><span class="sxs-lookup"><span data-stu-id="451e6-135">Referencing Sample Code from Conceptual Articles</span></span>

<span data-ttu-id="451e6-136">Om du vill inkludera kod från [exempel databasen](https://github.com/Microsoft/Quantum)kan du göra det med hjälp av ett särskilt DocFX markdown-kommando:</span><span class="sxs-lookup"><span data-stu-id="451e6-136">If you want to include code from the [samples repository](https://github.com/Microsoft/Quantum), you can do so using a special DocFX-Flavored Markdown command:</span></span>

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

<span data-ttu-id="451e6-137">Det här kommandot importerar rader 4 till 8 av [ `Game.qs` filen från `chsh-game` exemplet](https://github.com/microsoft/Quantum/blob/master/samples/algorithms/chsh-game/Game.qs)och markerar dem som Q# kod för markering av syntax.</span><span class="sxs-lookup"><span data-stu-id="451e6-137">This command will import lines 4 to 8 of the [`Game.qs` file from the `chsh-game` sample](https://github.com/microsoft/Quantum/blob/master/samples/algorithms/chsh-game/Game.qs), marking them as Q# code for the purpose of syntax highlighting.</span></span>
<span data-ttu-id="451e6-138">Med det här kommandot kan du undvika att duplicera kod mellan konceptuella artiklar och exempel databasen, så att exempel koden i dokumentationen alltid är så aktuell som möjligt.</span><span class="sxs-lookup"><span data-stu-id="451e6-138">Using this command, you can avoid duplicating code between conceptual articles and the samples repository, so that sample code in documentation is always as up to date as possible.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="451e6-139">Bidrag till API-referenser</span><span class="sxs-lookup"><span data-stu-id="451e6-139">Contributing to the API References</span></span>

<span data-ttu-id="451e6-140">För att bidra till en förbättring av API-referenserna är det mest användbart att öppna en pull-begäran direkt på den kod som dokumenteras.</span><span class="sxs-lookup"><span data-stu-id="451e6-140">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="451e6-141">Varje funktion, åtgärd eller användardefinierad typ har stöd för en dokumentations kommentar (anges i `///` stället för `//` ).</span><span class="sxs-lookup"><span data-stu-id="451e6-141">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="451e6-142">När vi kompilerar varje version av Quantum Development Kit, används dessa kommentarer för att generera API-referensen vid https://docs.microsoft.com/qsharp/api/ , inklusive information om indata till och utdata från varje anrops man, antaganden om varje anrops bara och exempel på hur de kan användas.</span><span class="sxs-lookup"><span data-stu-id="451e6-142">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="451e6-143">Se till att du inte redigerar den genererade API-dokumentationen manuellt, eftersom filerna skrivs över med varje ny version.</span><span class="sxs-lookup"><span data-stu-id="451e6-143">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="451e6-144">Vi använder oss av ditt bidrag till communityn och vill se till att ändringarna fortsätter att hjälpa användarna att lansera efter lanseringen.</span><span class="sxs-lookup"><span data-stu-id="451e6-144">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="451e6-145">Anta till exempel funktionen `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="451e6-145">For example, consider the function `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="451e6-146">En dokumentations kommentar bör hjälpa en användare att lära sig hur man tolkar `bits` och `oracle` och vad funktionen är för.</span><span class="sxs-lookup"><span data-stu-id="451e6-146">A documentation comment should help a user learn how to interpret `bits` and `oracle` and what the function is for.</span></span>
<span data-ttu-id="451e6-147">Var och en av dessa olika delar av information kan ges till Q# kompilatorn med ett särskilt namngivet markdown-avsnitt i dokumentations kommentaren.</span><span class="sxs-lookup"><span data-stu-id="451e6-147">Each of these different pieces of information can be provided to the Q# compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="451e6-148">Vi kan till exempel `ControlledOnBitString` skriva något som liknar följande:</span><span class="sxs-lookup"><span data-stu-id="451e6-148">For the example of `ControlledOnBitString`, we might write something like the following:</span></span>

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

<span data-ttu-id="451e6-149">Du kan se den återgivna versionen av koden ovan i API- [dokumentationen för `ControlledOnBitString` funktionen](xref:microsoft.quantum.canon.controlledonbitstring).</span><span class="sxs-lookup"><span data-stu-id="451e6-149">You can see the rendered version of the code above in the [API documentation for the `ControlledOnBitString` function](xref:microsoft.quantum.canon.controlledonbitstring).</span></span>

<span data-ttu-id="451e6-150">Förutom den allmänna metoden för dokumentations skrivning, i skriva API-dokumentation kommentarer, hjälper det till att hålla några saker i åtanke:</span><span class="sxs-lookup"><span data-stu-id="451e6-150">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="451e6-151">Formatet för varje dokumentations kommentar måste matcha vad Q# kompileraren förväntar sig att din dokumentation ska visas korrekt.</span><span class="sxs-lookup"><span data-stu-id="451e6-151">The format of each documentation comment has to match what the Q# compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="451e6-152">Vissa avsnitt, till exempel `/// # Remarks` för att tillåta fri hands innehåll, medan avsnitt som `/// # See Also` avsnittet är mer restriktiva.</span><span class="sxs-lookup"><span data-stu-id="451e6-152">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="451e6-153">En läsare kan läsa API-dokumentationen på huvud-API-referens webbplatsen, på sammanfattningen för varje namn område eller till och med i IDE genom att använda hov rings information.</span><span class="sxs-lookup"><span data-stu-id="451e6-153">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="451e6-154">Se till att det `/// # Summary` inte är längre än om en mening hjälper läsaren att snabbt sortera om de behöver läsa mer eller titta någon annan stans, och kan hjälpa till att snabbt söka igenom sammanfattningar av namn områden.</span><span class="sxs-lookup"><span data-stu-id="451e6-154">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="451e6-155">Dokumentationen kan vara mycket längre än själva koden, men det är OK!</span><span class="sxs-lookup"><span data-stu-id="451e6-155">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="451e6-156">Även en liten del av koden kan ha oväntade effekter för användare som inte känner till sammanhanget där koden finns.</span><span class="sxs-lookup"><span data-stu-id="451e6-156">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="451e6-157">Genom att tillhandahålla konkreta exempel och tydliga förklaringar kan du hjälpa användarna att göra den bästa användningen av den kod som är tillgänglig för dem.</span><span class="sxs-lookup"><span data-stu-id="451e6-157">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->
