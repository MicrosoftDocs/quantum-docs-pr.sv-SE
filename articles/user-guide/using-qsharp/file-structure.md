---
title: 'Q # fil struktur'
description: 'Beskriver strukturen och syntaxen för en Q #-fil.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: 54efc2b9d6b7f1956cdf9a335c88620b29f7729d
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884175"
---
# <a name="q-file-structure"></a><span data-ttu-id="1582d-103">Q # fil struktur</span><span class="sxs-lookup"><span data-stu-id="1582d-103">Q# File Structure</span></span>

<span data-ttu-id="1582d-104">En Q #-fil består av en sekvens med *namn områdes deklarationer*.</span><span class="sxs-lookup"><span data-stu-id="1582d-104">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="1582d-105">Varje namn områdes deklaration innehåller deklarationer för användardefinierade typer, åtgärder och funktioner och kan innehålla valfritt antal varje typ av deklaration och i vilken ordning som helst.</span><span class="sxs-lookup"><span data-stu-id="1582d-105">Each namespace declaration contains declarations for user-defined types, operations, and functions, and can contain any number of each type of declaration and in any order.</span></span>
<span data-ttu-id="1582d-106">Mer information om deklarationer i ett namn område finns i [användardefinierade typer](xref:microsoft.quantum.guide.types#user-defined-types), [åtgärder](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)och [funktioner](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span><span class="sxs-lookup"><span data-stu-id="1582d-106">For more information on declarations within a namespace, see [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span></span>

<span data-ttu-id="1582d-107">Den enda text som kan visas utanför en namn områdes deklaration är kommentarer.</span><span class="sxs-lookup"><span data-stu-id="1582d-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="1582d-108">I synnerhet är dokumentations kommentarer för ett namn område före deklarationen.</span><span class="sxs-lookup"><span data-stu-id="1582d-108">In particular, documentation comments for a namespace precede the declaration.</span></span> <span data-ttu-id="1582d-109">Mer information finns i [dokumentations kommentarer](#documentation-comments) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="1582d-109">For more information, see [Documentation comments](#documentation-comments) in this article.</span></span> 

## <a name="namespace-declarations"></a><span data-ttu-id="1582d-110">Namn områdes deklarationer</span><span class="sxs-lookup"><span data-stu-id="1582d-110">Namespace Declarations</span></span>

<span data-ttu-id="1582d-111">En Q #-fil har vanligt vis bara en namn områdes deklaration, men kan ha ingen (och vara tom eller bara innehålla kommentarer) eller innehålla flera namn områden.</span><span class="sxs-lookup"><span data-stu-id="1582d-111">A Q# file typically has just one namespace declaration, but could have none (and be empty or just contain comments) or could contain multiple namespaces.</span></span>
<span data-ttu-id="1582d-112">Namespace-deklarationer kan inte kapslas.</span><span class="sxs-lookup"><span data-stu-id="1582d-112">Namespace declarations can not be nested.</span></span>

<span data-ttu-id="1582d-113">Du kan deklarera samma namnrymd i flera Q #-filer som kompileras tillsammans, så länge det inte finns någon typ, åtgärd eller funktions deklaration med samma namn.</span><span class="sxs-lookup"><span data-stu-id="1582d-113">You can declare the same namespace in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="1582d-114">I synnerhet är det inte tillåtet att definiera samma typ i samma namnrymd i flera filer, även om deklarationerna är identiska.</span><span class="sxs-lookup"><span data-stu-id="1582d-114">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="1582d-115">En namn områdes deklaration består av nyckelordet `namespace` , följt av namnet på namn området och de deklarationer som finns i namn området som omges av klammerparenteser `{ }` .</span><span class="sxs-lookup"><span data-stu-id="1582d-115">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, and the declarations contained in the namespace enclosed in braces `{ }`.</span></span>
<span data-ttu-id="1582d-116">Namn rymds namn följer .NET-mönstret för en sekvens med en eller flera juridiska symboler avgränsade med punkter `.` .</span><span class="sxs-lookup"><span data-stu-id="1582d-116">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="1582d-117">Till exempel `MyQuantumStuff` och `Microsoft.Quantum.Intrinsic` är giltiga namn områdes namn.</span><span class="sxs-lookup"><span data-stu-id="1582d-117">For example, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="1582d-118">I konvention är det dock inte obligatoriskt att använda versaler i namn områdes namn.</span><span class="sxs-lookup"><span data-stu-id="1582d-118">By convention, capitalize the symbols in a namespace name, however, this is not required.</span></span>

<span data-ttu-id="1582d-119">Referenser till typer eller callables som deklarerats närmare i en fil matchas korrekt. Det finns inget behov av typen, åtgärden eller funktions deklarationen att föregå en referens till den.</span><span class="sxs-lookup"><span data-stu-id="1582d-119">References to types or callables declared further down in a file resolve properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="1582d-120">Öppna direktiv</span><span class="sxs-lookup"><span data-stu-id="1582d-120">Open Directives</span></span>

<span data-ttu-id="1582d-121">I ett namn områdes block använder du `open` direktivet för att importera alla typer och callables som har deklarerats i ett visst namn område och referera till dem med hjälp av okvalificerade namn.</span><span class="sxs-lookup"><span data-stu-id="1582d-121">Within a namespace block, use the `open` directive to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="1582d-122">Ett sådant `open` direktiv består av `open` nyckelordet följt av namn området som ska öppnas och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="1582d-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="1582d-123">Alla `open` direktiv måste finnas före eventuella `function` -, `operation` -eller- `newtype` deklarationer i blocket namespace.</span><span class="sxs-lookup"><span data-stu-id="1582d-123">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="1582d-124">Alternativt kan du definiera ett kort namn för det öppnade namn området.</span><span class="sxs-lookup"><span data-stu-id="1582d-124">Optionally, you can define a short name for the opened namespace.</span></span> <span data-ttu-id="1582d-125">Om ett kort namn har definierats måste du kvalificera alla element från det namn området med det definierade korta namnet.</span><span class="sxs-lookup"><span data-stu-id="1582d-125">If a short name is defined, you must qualify all elements from that namespace by the defined short name.</span></span> <span data-ttu-id="1582d-126">Till exempel, med följande namn rymds deklaration och öppna direktiv,</span><span class="sxs-lookup"><span data-stu-id="1582d-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="1582d-127">om en deklarerad åtgärd använder en åtgärd `Op` från `Microsoft.Quantum.Intrinsic` , anropar du den genom att bara använda `Op` .</span><span class="sxs-lookup"><span data-stu-id="1582d-127">if a declared operation uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, you call it by simply using `Op`.</span></span>
<span data-ttu-id="1582d-128">För att anropa en viss funktion `Fn` från `Microsoft.Quantum.Math` måste du dock anropa den med hjälp av `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="1582d-128">However, to call a certain function `Fn` from `Microsoft.Quantum.Math`, you must call it using `Math.Fn`.</span></span>

<span data-ttu-id="1582d-129">`open`Direktivet gäller hela namn områdes blocket i en fil.</span><span class="sxs-lookup"><span data-stu-id="1582d-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="1582d-130">Om du definierar ytterligare ett namn område i samma Q #-fil som `NS` tidigare, skulle alla åtgärder/funktioner/typer som definierats i den andra namn rymden inte ha åtkomst till något från `Microsoft.Quantum.Intrinsic` eller `Microsoft.Quantum.Math` om du inte upprepade de öppna direktiven där.</span><span class="sxs-lookup"><span data-stu-id="1582d-130">Hence, if you define an additional namespace in the same Q# file as `NS` earlier, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless you repeated the open directives therein.</span></span> 

<span data-ttu-id="1582d-131">Om du vill referera till en typ eller en anropad typ som är definierad i en annan namnrymd som *inte* är öppen i det aktuella namn området, måste du referera till den efter dess fullständiga namn.</span><span class="sxs-lookup"><span data-stu-id="1582d-131">To reference a type or callable defined in another namespace that is *not* opened in the current namespace, you must reference it by its fully-qualified name.</span></span>
<span data-ttu-id="1582d-132">Till exempel, med en åtgärd `Op` som heter från `X.Y` namn området:</span><span class="sxs-lookup"><span data-stu-id="1582d-132">For example, given an operation named `Op` from the `X.Y` namespace:</span></span>

* <span data-ttu-id="1582d-133">Du måste referera till det med fullständigt kvalificerat namn `X.Y.Op` , om inte `X.Y` namn området har öppnats tidigare i det aktuella blocket.</span><span class="sxs-lookup"><span data-stu-id="1582d-133">You must reference it by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> 
* <span data-ttu-id="1582d-134">Även om `X` namn området öppnas är det inte möjligt att referera till åtgärden som `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="1582d-134">Even if the `X` namespace is opened, it is not possible to reference the operation as `Y.Op`.</span></span>
* <span data-ttu-id="1582d-135">Om du har definierat det korta namnet `Z` för `X.Y` i namn området och filen måste du referera till `Op` som `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="1582d-135">If you defined the short name `Z` for `X.Y` in that namespace and file, you must reference `Op` as `Z.Op`.</span></span> 

<span data-ttu-id="1582d-136">Det är vanligt vis bättre att inkludera ett namn område med hjälp av ett `open` direktiv.</span><span class="sxs-lookup"><span data-stu-id="1582d-136">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="1582d-137">Att använda ett fullständigt kvalificerat namn krävs om två namn rymder definierar konstruktioner med samma namn och den aktuella källan använder konstruktioner från båda.</span><span class="sxs-lookup"><span data-stu-id="1582d-137">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="1582d-138">Q # följer samma regler för namngivning som andra .NET-språk.</span><span class="sxs-lookup"><span data-stu-id="1582d-138">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="1582d-139">Q # stöder dock inte relativa referenser till namn områden.</span><span class="sxs-lookup"><span data-stu-id="1582d-139">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="1582d-140">Om namn området till exempel `a.b` är öppet matchas inte en referens till en åtgärd `c.d` med *not* namnet med fullständigt namn `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="1582d-140">For example, if the namespace `a.b` is open, a reference to an operation named `c.d` does *not* resolve to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="1582d-141">Formatering</span><span class="sxs-lookup"><span data-stu-id="1582d-141">Formatting</span></span>

<span data-ttu-id="1582d-142">De flesta Q #-instruktioner och direktiv slutar med ett avslutande semikolon `;` .</span><span class="sxs-lookup"><span data-stu-id="1582d-142">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="1582d-143">Instruktioner och deklarationer som `for` och `operation` som slutar med ett instruktions block (se följande avsnitt) kräver inte ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="1582d-143">Statements and declarations such as `for` and `operation` that end with a statement block (see the following section) do not require a terminating semicolon.</span></span>
<span data-ttu-id="1582d-144">Varje instruktions Beskrivning noterar om avslutande semikolon krävs.</span><span class="sxs-lookup"><span data-stu-id="1582d-144">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="1582d-145">Instruktioner, som uttryck, deklarationer och direktiv, kan delas upp över flera rader.</span><span class="sxs-lookup"><span data-stu-id="1582d-145">Statements, like expressions, declarations, and directives, can be broken out across multiple lines.</span></span>
<span data-ttu-id="1582d-146">Undvik att placera flera instruktioner på en enda rad.</span><span class="sxs-lookup"><span data-stu-id="1582d-146">Avoid putting multiple statements on a single line.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="1582d-147">Instruktions block</span><span class="sxs-lookup"><span data-stu-id="1582d-147">Statement Blocks</span></span>

<span data-ttu-id="1582d-148">Q #-instruktioner grupperas i instruktions block, vilka ingår i klammerparenteser `{ }` .</span><span class="sxs-lookup"><span data-stu-id="1582d-148">Q# statements are grouped into statement blocks, which are contained with braces `{ }`.</span></span> <span data-ttu-id="1582d-149">Ett instruktions block börjar med en inledande `{` och slutar med en stängning `}` .</span><span class="sxs-lookup"><span data-stu-id="1582d-149">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="1582d-150">Ett instruktions block som är lexikalt omslutet i ett annat block anses vara ett under block av det innehåll ande blocket. innehåller och underordnade block kallas även för yttre och inre block.</span><span class="sxs-lookup"><span data-stu-id="1582d-150">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="1582d-151">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="1582d-151">Comments</span></span>

<span data-ttu-id="1582d-152">Kommentarer börjar med två snedstreck, `//` och fortsätter till slutet av raden.</span><span class="sxs-lookup"><span data-stu-id="1582d-152">Comments begin with two forward slashes, `//`, and continue until the end of the line.</span></span>
<span data-ttu-id="1582d-153">En kommentar kan finnas var som helst i en Q #-källfil.</span><span class="sxs-lookup"><span data-stu-id="1582d-153">A comment can appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="1582d-154">Dokumentations kommentarer</span><span class="sxs-lookup"><span data-stu-id="1582d-154">Documentation Comments</span></span>

<span data-ttu-id="1582d-155">Kommentarer som börjar med tre snedstreck, `///` behandlas särskilt av kompilatorn när de visas omedelbart före en namnrymd, åtgärd, specialisering, funktion eller typ definition.</span><span class="sxs-lookup"><span data-stu-id="1582d-155">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="1582d-156">I så fall behandlar kompileraren dem som dokumentation för den definierade typen av anropad eller användardefinierad typ, samma som andra .NET-språk.</span><span class="sxs-lookup"><span data-stu-id="1582d-156">In that case, the compiler treats them as documentation for the defined callable or user-defined type, the same as other .NET languages.</span></span>

<span data-ttu-id="1582d-157">I `///` kommentarer är text som ska visas som en del av API-dokumentationen formaterad som [markdown](https://daringfireball.net/projects/markdown/syntax), med olika delar av dokumentationen som anges av särskilt namngivna huvuden.</span><span class="sxs-lookup"><span data-stu-id="1582d-157">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation indicated by specially-named headers.</span></span>
<span data-ttu-id="1582d-158">I markdown använder du `@"<ref target>"` tillägget för kors referens åtgärder, funktioner och användardefinierade typer i Q #.</span><span class="sxs-lookup"><span data-stu-id="1582d-158">In Markdown, use the `@"<ref target>"` extension to cross-reference operations, functions, and user-defined types in Q#.</span></span> <span data-ttu-id="1582d-159">Ersätt `<ref target>` med det fullständigt kvalificerade namnet på det refererade kodvärdet.</span><span class="sxs-lookup"><span data-stu-id="1582d-159">Replace `<ref target>` with the fully qualified name of the referenced code object.</span></span>
<span data-ttu-id="1582d-160">Olika dokumentations motorer kan också ha stöd för ytterligare markdown-tillägg.</span><span class="sxs-lookup"><span data-stu-id="1582d-160">Different documentation engines may also support additional Markdown extensions.</span></span>

<span data-ttu-id="1582d-161">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="1582d-161">For example:</span></span>

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

<span data-ttu-id="1582d-162">Följande namn är giltiga som dokumentation kommentars rubriker.</span><span class="sxs-lookup"><span data-stu-id="1582d-162">The following names are valid as documentation comment headers.</span></span>

- <span data-ttu-id="1582d-163">**Sammanfattning**: en kort sammanfattning av beteendet för en funktion eller åtgärd eller syftet med en typ.</span><span class="sxs-lookup"><span data-stu-id="1582d-163">**Summary**: A short summary of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="1582d-164">Det första stycket i sammanfattningen används för hov rings information.</span><span class="sxs-lookup"><span data-stu-id="1582d-164">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="1582d-165">Det bör vara oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="1582d-165">It should be plain text.</span></span>
- <span data-ttu-id="1582d-166">**Beskrivning**: en beskrivning av beteendet för en funktion eller åtgärd, eller syftet med en typ.</span><span class="sxs-lookup"><span data-stu-id="1582d-166">**Description**: A description of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="1582d-167">Tillsammans utgör sammanfattningen och beskrivningen den genererade dokumentations filen för funktionen, åtgärden eller typen.</span><span class="sxs-lookup"><span data-stu-id="1582d-167">Together, the summary and description form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="1582d-168">Beskrivningen stöder LaTeX symboler och ekvationer som är formaterade i rad.</span><span class="sxs-lookup"><span data-stu-id="1582d-168">The description supports in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="1582d-169">**Inmatade**: en beskrivning av indataströmmen för en funktion eller funktion.</span><span class="sxs-lookup"><span data-stu-id="1582d-169">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="1582d-170">Kan innehålla ytterligare markdown-underavsnitt som anger varje element i indataströmmen.</span><span class="sxs-lookup"><span data-stu-id="1582d-170">Can contain additional Markdown subsections indicating each element of the input tuple.</span></span>
- <span data-ttu-id="1582d-171">**Utdata**: en beskrivning av tuppeln som returneras av en åtgärd eller funktion.</span><span class="sxs-lookup"><span data-stu-id="1582d-171">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="1582d-172">**Typ parametrar**: ett tomt avsnitt som innehåller ett ytterligare underavsnitt för varje generisk typ parameter.</span><span class="sxs-lookup"><span data-stu-id="1582d-172">**Type Parameters**: An empty section that contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="1582d-173">**Exempel**: ett kort exempel på en åtgärd, funktion eller typ som används.</span><span class="sxs-lookup"><span data-stu-id="1582d-173">**Example**: A short example of the operation, function, or type in use.</span></span>
- <span data-ttu-id="1582d-174">**Anmärkningar**: Diverse Prose som beskriver viss aspekt av åtgärden, funktionen eller typen.</span><span class="sxs-lookup"><span data-stu-id="1582d-174">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="1582d-175">**Se även**: en lista över fullständigt kvalificerade namn som visar relaterade funktioner, åtgärder eller användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="1582d-175">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="1582d-176">**Referenser**: en lista över referenser och citat för det dokumenterade objektet.</span><span class="sxs-lookup"><span data-stu-id="1582d-176">**References**: A list of references and citations for the documented item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1582d-177">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="1582d-177">Next steps</span></span>

<span data-ttu-id="1582d-178">Lär dig mer om [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions) i Q #.</span><span class="sxs-lookup"><span data-stu-id="1582d-178">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>