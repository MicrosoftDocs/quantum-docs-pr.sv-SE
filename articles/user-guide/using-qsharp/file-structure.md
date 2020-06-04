---
title: 'Q # fil struktur'
description: 'Beskriver strukturen och syntaxen för en Q #-fil.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327466"
---
# <a name="q-file-structure"></a><span data-ttu-id="804b0-103">Q # fil struktur</span><span class="sxs-lookup"><span data-stu-id="804b0-103">Q# File Structure</span></span>

<span data-ttu-id="804b0-104">Varje Q #-åtgärd, funktion och användardefinierad typ definieras i ett namn område.</span><span class="sxs-lookup"><span data-stu-id="804b0-104">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>

<span data-ttu-id="804b0-105">En Q #-fil består av en sekvens med *namn områdes deklarationer*.</span><span class="sxs-lookup"><span data-stu-id="804b0-105">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="804b0-106">Varje namn områdes deklaration innehåller deklarationer för användardefinierade typer, åtgärder och funktioner.</span><span class="sxs-lookup"><span data-stu-id="804b0-106">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="804b0-107">En namn områdes deklaration får innehålla valfritt antal av varje typ av deklaration, och i vilken ordning som helst.</span><span class="sxs-lookup"><span data-stu-id="804b0-107">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="804b0-108">Följ dessa länkar om du vill ha mer information om att deklarera [användardefinierade typer](xref:microsoft.quantum.guide.types#user-defined-types), [åtgärder](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)och [funktioner](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) inom ett namn område.</span><span class="sxs-lookup"><span data-stu-id="804b0-108">Follow these links for more details on declaring [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) within a namespace.</span></span>

<span data-ttu-id="804b0-109">Den enda text som kan visas utanför en namn områdes deklaration är kommentarer.</span><span class="sxs-lookup"><span data-stu-id="804b0-109">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="804b0-110">I synnerhet dokumentations kommentarer (mer information nedan) för ett namn område före deklarationen.</span><span class="sxs-lookup"><span data-stu-id="804b0-110">In particular, documentation comments (more details below) for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="804b0-111">Namn områdes deklarationer</span><span class="sxs-lookup"><span data-stu-id="804b0-111">Namespace Declarations</span></span>

<span data-ttu-id="804b0-112">En Q #-fil har vanligt vis exakt en namn områdes deklaration, men kan ha ingen (och vara tom eller bara innehålla kommentarer) eller innehålla flera namn områden.</span><span class="sxs-lookup"><span data-stu-id="804b0-112">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="804b0-113">Namespace-deklarationer får inte vara kapslade.</span><span class="sxs-lookup"><span data-stu-id="804b0-113">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="804b0-114">Samma namnrymd kan deklareras i flera Q #-filer som kompileras tillsammans, så länge det inte finns någon typ, åtgärd eller funktions deklaration med samma namn.</span><span class="sxs-lookup"><span data-stu-id="804b0-114">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="804b0-115">I synnerhet är det inte tillåtet att definiera samma typ i samma namnrymd i flera filer, även om deklarationerna är identiska.</span><span class="sxs-lookup"><span data-stu-id="804b0-115">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="804b0-116">En namn områdes deklaration består av nyckelordet `namespace` följt av namnet på namn området, en öppen klammerparentes `{` , de deklarationer som finns i namn området och en avslutande klammerparentes `}` .</span><span class="sxs-lookup"><span data-stu-id="804b0-116">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="804b0-117">Namn rymds namn följer .NET-mönstret för en sekvens med en eller flera juridiska symboler avgränsade med punkter `.` .</span><span class="sxs-lookup"><span data-stu-id="804b0-117">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="804b0-118">Till exempel, `MyQuantumStuff` och `Microsoft.Quantum.Intrinsic` är giltiga namn områdes namn.</span><span class="sxs-lookup"><span data-stu-id="804b0-118">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="804b0-119">Enligt konvention är symbolerna i namn områdes namnet versaler, men det är inget krav.</span><span class="sxs-lookup"><span data-stu-id="804b0-119">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="804b0-120">Referenser till typer eller callables som deklarerats senare i en fil löses korrekt. Det finns inget behov av typen, åtgärden eller funktions deklarationen att föregå en referens till den.</span><span class="sxs-lookup"><span data-stu-id="804b0-120">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="804b0-121">Öppna direktiv</span><span class="sxs-lookup"><span data-stu-id="804b0-121">Open Directives</span></span>

<span data-ttu-id="804b0-122">I ett namn områdes block `open` kan direktivet användas för att importera alla typer och callables som har deklarerats i ett visst namn område och referera till dem med hjälp av okvalificerade namn.</span><span class="sxs-lookup"><span data-stu-id="804b0-122">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="804b0-123">Ett sådant `open` direktiv består av `open` nyckelordet följt av namn området som ska öppnas och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="804b0-123">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="804b0-124">Alla `open` direktiv måste finnas före eventuella `function` -, `operation` -eller- `newtype` deklarationer i blocket namespace.</span><span class="sxs-lookup"><span data-stu-id="804b0-124">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="804b0-125">Alternativt kan ett kort namn för det öppna namn området definieras så att alla element från det namn området kan (och behöver) kvalificeras av det definierade korta namnet.</span><span class="sxs-lookup"><span data-stu-id="804b0-125">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="804b0-126">Till exempel, med följande namn rymds deklaration och öppna direktiv,</span><span class="sxs-lookup"><span data-stu-id="804b0-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="804b0-127">om en åtgärd som vi deklarerar använder en åtgärd `Op` från `Microsoft.Quantum.Intrinsic` , skulle vi kalla den genom att bara använda `Op` .</span><span class="sxs-lookup"><span data-stu-id="804b0-127">if an operation we declare uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, we would call it by simply using `Op`.</span></span>
<span data-ttu-id="804b0-128">Men om vi ville ha ett anrop till en viss funktion `Fn` från `Microsoft.Quantum.Math` skulle vi behöva anropa det med `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="804b0-128">However, if we wanted a call a certain function `Fn` from `Microsoft.Quantum.Math`, we would need to call it using `Math.Fn`.</span></span>

<span data-ttu-id="804b0-129">`open`Direktivet gäller hela namn områdes blocket i en fil.</span><span class="sxs-lookup"><span data-stu-id="804b0-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="804b0-130">Om vi till exempel skulle definiera ytterligare ett namn område i samma Q #-fil som `NS` ovan, skulle alla åtgärder/funktioner/typer som definierats i den andra namn rymden inte ha åtkomst till något från `Microsoft.Quantum.Intrinsic` eller `Microsoft.Quantum.Math` om vi upprepade de öppna direktiven i fråga.</span><span class="sxs-lookup"><span data-stu-id="804b0-130">Hence, if we were to define an additional namespace in the same Q# file as `NS` above, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless we repeated the open directives therein.</span></span> 

<span data-ttu-id="804b0-131">En typ eller en anropad typ som har definierats i en annan namnrymd som *inte* är öppen i det aktuella namn området måste refereras till av sitt fullständigt kvalificerade namn.</span><span class="sxs-lookup"><span data-stu-id="804b0-131">A type or callable defined in another namespace that is *not* opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="804b0-132">Till exempel måste en åtgärd `Op` som heter från `X.Y` namn området refereras till av sitt fullständigt kvalificerade namn `X.Y.Op` , om inte `X.Y` namn området har öppnats tidigare i det aktuella blocket.</span><span class="sxs-lookup"><span data-stu-id="804b0-132">For example, an operation named `Op` from the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="804b0-133">Som nämnts ovan, även om `X` namn området har öppnats, är det inte möjligt att referera till åtgärden som `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="804b0-133">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="804b0-134">Om ett kort namn `Z` för `X.Y` har definierats i namn området och filen, `Op` måste det kallas `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="804b0-134">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

<span data-ttu-id="804b0-135">Det är vanligt vis bättre att inkludera ett namn område med hjälp av ett `open` direktiv.</span><span class="sxs-lookup"><span data-stu-id="804b0-135">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="804b0-136">Att använda ett fullständigt kvalificerat namn krävs om två namn rymder definierar konstruktioner med samma namn och den aktuella källan använder konstruktioner från båda.</span><span class="sxs-lookup"><span data-stu-id="804b0-136">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="804b0-137">Q # följer samma regler för namngivning som andra .NET-språk.</span><span class="sxs-lookup"><span data-stu-id="804b0-137">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="804b0-138">Q # stöder dock inte relativa referenser till namn områden.</span><span class="sxs-lookup"><span data-stu-id="804b0-138">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="804b0-139">Det vill säga, om namn området `a.b` har öppnats, matchas inte en referens till en åtgärd `c.d` med namnet i en åtgärd med fullständigt namn *not* `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="804b0-139">That is, if the namespace `a.b` has been opened, a reference to an operation named `c.d` will *not* be resolved to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="804b0-140">Formatering</span><span class="sxs-lookup"><span data-stu-id="804b0-140">Formatting</span></span>

<span data-ttu-id="804b0-141">De flesta Q #-instruktioner och direktiv slutar med ett avslutande semikolon `;` .</span><span class="sxs-lookup"><span data-stu-id="804b0-141">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="804b0-142">Instruktioner och deklarationer som `for` och `operation` som slutar med ett instruktions block (se nedan) kräver inte ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="804b0-142">Statements and declarations such as `for` and `operation` that end with a statement block (see below) do not require a terminating semicolon.</span></span>
<span data-ttu-id="804b0-143">Varje instruktions Beskrivning noterar om avslutande semikolon krävs.</span><span class="sxs-lookup"><span data-stu-id="804b0-143">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="804b0-144">Instruktioner, som uttryck, deklarationer och direktiv, kan delas upp över flera rader.</span><span class="sxs-lookup"><span data-stu-id="804b0-144">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="804b0-145">Att ha flera instruktioner på en enda rad bör undvikas.</span><span class="sxs-lookup"><span data-stu-id="804b0-145">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="804b0-146">Instruktions block</span><span class="sxs-lookup"><span data-stu-id="804b0-146">Statement Blocks</span></span>

<span data-ttu-id="804b0-147">Q #-instruktioner grupperas i uttrycks block.</span><span class="sxs-lookup"><span data-stu-id="804b0-147">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="804b0-148">Ett instruktions block börjar med en inledande `{` och slutar med en stängning `}` .</span><span class="sxs-lookup"><span data-stu-id="804b0-148">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="804b0-149">Ett instruktions block som är lexikalt omslutet i ett annat block anses vara ett under block av det innehåll ande blocket. innehåller och underordnade block kallas även för yttre och inre block.</span><span class="sxs-lookup"><span data-stu-id="804b0-149">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="804b0-150">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="804b0-150">Comments</span></span>

<span data-ttu-id="804b0-151">Kommentarer börjar med två snedstreck, `//` och fortsätter till slutet av raden.</span><span class="sxs-lookup"><span data-stu-id="804b0-151">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="804b0-152">En kommentar kan visas var som helst i en Q #-källfil.</span><span class="sxs-lookup"><span data-stu-id="804b0-152">A comment may appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="804b0-153">Dokumentations kommentarer</span><span class="sxs-lookup"><span data-stu-id="804b0-153">Documentation Comments</span></span>

<span data-ttu-id="804b0-154">Kommentarer som börjar med tre snedstreck, `///` behandlas särskilt av kompilatorn när de visas omedelbart före en namnrymd, åtgärd, specialisering, funktion eller typ definition.</span><span class="sxs-lookup"><span data-stu-id="804b0-154">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="804b0-155">I så fall tas deras innehåll som dokumentation för den definierade typen av anropad eller användardefinierad typ, som för andra .NET-språk.</span><span class="sxs-lookup"><span data-stu-id="804b0-155">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="804b0-156">I `///` kommentarer är text som ska visas som en del av API-dokumentationen formaterad som [markdown](https://daringfireball.net/projects/markdown/syntax), med olika delar av dokumentationen som anges av särskilt namngivna huvuden.</span><span class="sxs-lookup"><span data-stu-id="804b0-156">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="804b0-157">Som tillägg till markdown kan kors referenser till åtgärder, funktioner och användardefinierade typer i Q # inkluderas med `@"<ref target>"` , där `<ref target>` ersätts av det fullständigt kvalificerade namnet på det kod objekt som refereras till.</span><span class="sxs-lookup"><span data-stu-id="804b0-157">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="804b0-158">Alternativt kan en dokumentations motor också ha stöd för ytterligare markdown-tillägg.</span><span class="sxs-lookup"><span data-stu-id="804b0-158">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="804b0-159">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="804b0-159">For example:</span></span>

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="804b0-160">Följande namn identifieras som dokumentations kommentars rubriker.</span><span class="sxs-lookup"><span data-stu-id="804b0-160">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="804b0-161">**Sammanfattning**: en kort sammanfattning av beteendet för en funktion eller åtgärd, eller av syftet av en typ.</span><span class="sxs-lookup"><span data-stu-id="804b0-161">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="804b0-162">Det första stycket i sammanfattningen används för hov rings information.</span><span class="sxs-lookup"><span data-stu-id="804b0-162">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="804b0-163">Det bör vara oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="804b0-163">It should be plain text.</span></span>
- <span data-ttu-id="804b0-164">**Beskrivning**: en beskrivning av beteendet för en funktion eller åtgärd, eller syftet med en typ.</span><span class="sxs-lookup"><span data-stu-id="804b0-164">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="804b0-165">Sammanfattningen och beskrivningen sammanfogas för att bilda den genererade dokumentations filen för funktionen, åtgärden eller typen.</span><span class="sxs-lookup"><span data-stu-id="804b0-165">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="804b0-166">Beskrivningen får innehålla infogade symboler och ekvationer med LaTeX-format.</span><span class="sxs-lookup"><span data-stu-id="804b0-166">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="804b0-167">**Inmatade**: en beskrivning av indataströmmen för en funktion eller funktion.</span><span class="sxs-lookup"><span data-stu-id="804b0-167">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="804b0-168">Kan innehålla ytterligare markdown-underavsnitt som anger varje enskilt element i indataströmmen.</span><span class="sxs-lookup"><span data-stu-id="804b0-168">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="804b0-169">**Utdata**: en beskrivning av tuppeln som returneras av en åtgärd eller funktion.</span><span class="sxs-lookup"><span data-stu-id="804b0-169">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="804b0-170">**Typ parametrar**: ett tomt avsnitt som innehåller ytterligare ett underavsnitt för varje generisk typ parameter.</span><span class="sxs-lookup"><span data-stu-id="804b0-170">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="804b0-171">**Exempel**: ett kort exempel på en åtgärd, funktion eller typ som används.</span><span class="sxs-lookup"><span data-stu-id="804b0-171">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="804b0-172">**Anmärkningar**: Diverse Prose som beskriver viss aspekt av åtgärden, funktionen eller typen.</span><span class="sxs-lookup"><span data-stu-id="804b0-172">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="804b0-173">**Se även**: en lista över fullständigt kvalificerade namn som visar relaterade funktioner, åtgärder eller användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="804b0-173">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="804b0-174">**Referenser**: en lista över referenser och citat för det objekt som dokumenteras.</span><span class="sxs-lookup"><span data-stu-id="804b0-174">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="next-steps"></a><span data-ttu-id="804b0-175">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="804b0-175">Next steps</span></span>

<span data-ttu-id="804b0-176">Lär dig mer om [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions) i Q #.</span><span class="sxs-lookup"><span data-stu-id="804b0-176">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>