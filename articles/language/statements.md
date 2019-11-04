---
title: 'Q #-instruktioner | Microsoft Docs'
description: 'Q #-instruktioner'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5bcbee868c76aaf53d0b7969e6e634da62689aaa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184873"
---
# <a name="statements-and-other-constructs"></a><span data-ttu-id="6e38f-103">Instruktioner och andra konstruktioner</span><span class="sxs-lookup"><span data-stu-id="6e38f-103">Statements and Other Constructs</span></span>

## <a name="comments"></a><span data-ttu-id="6e38f-104">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6e38f-104">Comments</span></span>

<span data-ttu-id="6e38f-105">Kommentarer börjar med två snedstreck, `//`och fortsätter till slutet av raden.</span><span class="sxs-lookup"><span data-stu-id="6e38f-105">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="6e38f-106">En kommentar kan visas var som helst i en Q #-källfil.</span><span class="sxs-lookup"><span data-stu-id="6e38f-106">A comment may appear anywhere in a Q# source file.</span></span>

### <a name="documentation-comments"></a><span data-ttu-id="6e38f-107">Dokumentations kommentarer</span><span class="sxs-lookup"><span data-stu-id="6e38f-107">Documentation Comments</span></span>

<span data-ttu-id="6e38f-108">Kommentarer som börjar med tre snedstreck, `///`, behandlas särskilt av kompilatorn när de visas omedelbart före en namnrymd, åtgärd, specialisering, funktion eller typ definition.</span><span class="sxs-lookup"><span data-stu-id="6e38f-108">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="6e38f-109">I så fall tas deras innehåll som dokumentation för den definierade typen av anropad eller användardefinierad typ, som för andra .NET-språk.</span><span class="sxs-lookup"><span data-stu-id="6e38f-109">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="6e38f-110">I `///` kommentarer formateras text som en del av API-dokumentationen som [markdown](https://daringfireball.net/projects/markdown/syntax), med olika delar av dokumentationen som anges av särskilt namngivna huvuden.</span><span class="sxs-lookup"><span data-stu-id="6e38f-110">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="6e38f-111">Som tillägg till markdown kan kors referenser till åtgärder, funktioner och användardefinierade typer i Q # inkluderas med hjälp av `@"<ref target>"`, där `<ref target>` ersätts av det fullständigt kvalificerade namnet på det kod objekt som refereras till.</span><span class="sxs-lookup"><span data-stu-id="6e38f-111">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="6e38f-112">Alternativt kan en dokumentations motor också ha stöd för ytterligare markdown-tillägg.</span><span class="sxs-lookup"><span data-stu-id="6e38f-112">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="6e38f-113">Exempel:</span><span class="sxs-lookup"><span data-stu-id="6e38f-113">For example:</span></span>

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
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit
{
    op(target);
    op(target);
}
```

<span data-ttu-id="6e38f-114">Följande namn identifieras som dokumentations kommentars rubriker.</span><span class="sxs-lookup"><span data-stu-id="6e38f-114">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="6e38f-115">**Sammanfattning**: en kort sammanfattning av beteendet för en funktion eller åtgärd, eller av syftet av en typ.</span><span class="sxs-lookup"><span data-stu-id="6e38f-115">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="6e38f-116">Det första stycket i sammanfattningen används för hov rings information.</span><span class="sxs-lookup"><span data-stu-id="6e38f-116">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="6e38f-117">Det bör vara oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="6e38f-117">It should be plain text.</span></span>
- <span data-ttu-id="6e38f-118">**Beskrivning**: en beskrivning av beteendet för en funktion eller åtgärd, eller syftet med en typ.</span><span class="sxs-lookup"><span data-stu-id="6e38f-118">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="6e38f-119">Sammanfattningen och beskrivningen sammanfogas för att bilda den genererade dokumentations filen för funktionen, åtgärden eller typen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-119">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="6e38f-120">Beskrivningen får innehålla infogade symboler och ekvationer med LaTeX-format.</span><span class="sxs-lookup"><span data-stu-id="6e38f-120">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="6e38f-121">**Inmatade**: en beskrivning av indataströmmen för en funktion eller funktion.</span><span class="sxs-lookup"><span data-stu-id="6e38f-121">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="6e38f-122">Kan innehålla ytterligare markdown-underavsnitt som anger varje enskilt element i indataströmmen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-122">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="6e38f-123">**Utdata**: en beskrivning av tuppeln som returneras av en åtgärd eller funktion.</span><span class="sxs-lookup"><span data-stu-id="6e38f-123">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="6e38f-124">**Typ parametrar**: ett tomt avsnitt som innehåller ytterligare ett underavsnitt för varje generisk typ parameter.</span><span class="sxs-lookup"><span data-stu-id="6e38f-124">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="6e38f-125">**Exempel**: ett kort exempel på en åtgärd, funktion eller typ som används.</span><span class="sxs-lookup"><span data-stu-id="6e38f-125">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="6e38f-126">**Anmärkningar**: Diverse Prose som beskriver viss aspekt av åtgärden, funktionen eller typen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-126">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="6e38f-127">**Se även**: en lista över fullständigt kvalificerade namn som visar relaterade funktioner, åtgärder eller användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="6e38f-127">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="6e38f-128">**Referenser**: en lista över referenser och citat för det objekt som dokumenteras.</span><span class="sxs-lookup"><span data-stu-id="6e38f-128">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="namespaces"></a><span data-ttu-id="6e38f-129">Namnområden</span><span class="sxs-lookup"><span data-stu-id="6e38f-129">Namespaces</span></span>

<span data-ttu-id="6e38f-130">Varje Q #-åtgärd, funktion och användardefinierad typ definieras i ett namn område.</span><span class="sxs-lookup"><span data-stu-id="6e38f-130">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>
<span data-ttu-id="6e38f-131">Q # följer samma regler för namngivning som andra .NET-språk.</span><span class="sxs-lookup"><span data-stu-id="6e38f-131">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="6e38f-132">Q # stöder dock inte relativa referenser till namn områden.</span><span class="sxs-lookup"><span data-stu-id="6e38f-132">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="6e38f-133">Det vill säga, om namn området `a.b` har öppnats, matchas inte en referens till ett åtgärds namn `c.d` till en åtgärd med fullständigt namn `a.b.c.d`.</span><span class="sxs-lookup"><span data-stu-id="6e38f-133">That is, if the namespace `a.b` has been opened, a reference to an operation names `c.d` will not be resolved to an operation with full name `a.b.c.d`.</span></span>

<span data-ttu-id="6e38f-134">I ett namn områdes block kan `open`-direktivet användas för att importera alla typer och callables som har deklarerats i ett visst namn område och referera till dem med hjälp av okvalificerade namn.</span><span class="sxs-lookup"><span data-stu-id="6e38f-134">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span> <span data-ttu-id="6e38f-135">Alternativt kan ett kort namn för det öppna namn området definieras så att alla element från det namn området kan (och behöver) kvalificeras av det definierade korta namnet.</span><span class="sxs-lookup"><span data-stu-id="6e38f-135">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="6e38f-136">`open`-direktivet gäller hela namn områdes blocket i en fil.</span><span class="sxs-lookup"><span data-stu-id="6e38f-136">The `open` directive applies to the entire namespace block within a file.</span></span>

<span data-ttu-id="6e38f-137">En typ eller en anropad typ som har definierats i en annan namnrymd som inte är öppen i det aktuella namn området måste refereras till av sitt fullständigt kvalificerade namn.</span><span class="sxs-lookup"><span data-stu-id="6e38f-137">A type or callable defined in another namespace that is not opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="6e38f-138">Till exempel måste en åtgärd som heter `Op` i namn området `X.Y` refereras till av dess fullständigt kvalificerade namn `X.Y.Op`, om inte `X.Y`-namnområdet har öppnats tidigare i det aktuella blocket.</span><span class="sxs-lookup"><span data-stu-id="6e38f-138">For example, an operation named `Op` in the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="6e38f-139">Som nämnts ovan, även om `X`-namnområdet har öppnats, går det inte att referera till åtgärden som `Y.Op`.</span><span class="sxs-lookup"><span data-stu-id="6e38f-139">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="6e38f-140">Om ett kort namn `Z` för `X.Y` har definierats i det namn området och filen måste `Op` kallas `Z.Op`.</span><span class="sxs-lookup"><span data-stu-id="6e38f-140">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

```qsharp
namespace NS {

    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

<span data-ttu-id="6e38f-141">Det är vanligt vis bättre att inkludera ett namn område med hjälp av ett `open`-direktiv.</span><span class="sxs-lookup"><span data-stu-id="6e38f-141">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="6e38f-142">Att använda ett fullständigt kvalificerat namn krävs om två namn rymder definierar konstruktioner med samma namn och den aktuella källan använder konstruktioner från båda.</span><span class="sxs-lookup"><span data-stu-id="6e38f-142">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

## <a name="formatting"></a><span data-ttu-id="6e38f-143">Formatering</span><span class="sxs-lookup"><span data-stu-id="6e38f-143">Formatting</span></span>

<span data-ttu-id="6e38f-144">De flesta Q #-instruktioner och direktiv slutar med ett avslutande semikolon `;`.</span><span class="sxs-lookup"><span data-stu-id="6e38f-144">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="6e38f-145">Instruktioner och deklarationer som `for` och `operation` som slutar med ett instruktions block kräver inte ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="6e38f-145">Statements and declarations such as `for` and `operation` that end with a statement block do not require a terminating semicolon.</span></span>
<span data-ttu-id="6e38f-146">Varje instruktions Beskrivning noterar om avslutande semikolon krävs.</span><span class="sxs-lookup"><span data-stu-id="6e38f-146">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="6e38f-147">Instruktioner, som uttryck, deklarationer och direktiv, kan delas upp över flera rader.</span><span class="sxs-lookup"><span data-stu-id="6e38f-147">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="6e38f-148">Att ha flera instruktioner på en enda rad bör undvikas.</span><span class="sxs-lookup"><span data-stu-id="6e38f-148">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="6e38f-149">Instruktions block</span><span class="sxs-lookup"><span data-stu-id="6e38f-149">Statement Blocks</span></span>

<span data-ttu-id="6e38f-150">Q #-instruktioner grupperas i uttrycks block.</span><span class="sxs-lookup"><span data-stu-id="6e38f-150">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="6e38f-151">Ett instruktions block börjar med en inledande `{` och slutar med en stängnings `}`.</span><span class="sxs-lookup"><span data-stu-id="6e38f-151">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="6e38f-152">Ett instruktions block som är lexikalt omslutet i ett annat block anses vara ett under block av det innehåll ande blocket. innehåller och underordnade block kallas även för yttre och inre block.</span><span class="sxs-lookup"><span data-stu-id="6e38f-152">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="symbol-binding-and-assignment"></a><span data-ttu-id="6e38f-153">Symbol bindning och tilldelning</span><span class="sxs-lookup"><span data-stu-id="6e38f-153">Symbol Binding and Assignment</span></span>

<span data-ttu-id="6e38f-154">Q # skiljer sig mellan föränderligt och oföränderliga symboler.</span><span class="sxs-lookup"><span data-stu-id="6e38f-154">Q# distinguishes between mutable and immutable symbols.</span></span>
<span data-ttu-id="6e38f-155">I allmänhet uppmuntras användningen av oföränderliga symboler eftersom den tillåter kompilatorn att utföra mer optimeringar.</span><span class="sxs-lookup"><span data-stu-id="6e38f-155">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="6e38f-156">Den vänstra sidan av bindningen består av en symbol tupel och den högra sidan av ett uttryck.</span><span class="sxs-lookup"><span data-stu-id="6e38f-156">The left-hand-side of the binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

<span data-ttu-id="6e38f-157">Eftersom alla Q #-typer är värde typer – med qubits tar en lite speciell roll – en "kopia" skapas när ett värde är kopplat till en symbol eller när en symbol har bundits.</span><span class="sxs-lookup"><span data-stu-id="6e38f-157">Since all Q# types are value types - with the qubits taking a somewhat special role - formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="6e38f-158">Detta är att säga att Q # är detsamma som om en kopia skapades för tilldelningen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-158">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span> <span data-ttu-id="6e38f-159">Detta omfattar även matriser.</span><span class="sxs-lookup"><span data-stu-id="6e38f-159">This in particular also includes arrays.</span></span> <span data-ttu-id="6e38f-160">Naturligtvis i praktiken är det bara de relevanta delarna som faktiskt återskapas vid behov.</span><span class="sxs-lookup"><span data-stu-id="6e38f-160">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

### <a name="tuple-deconstruction"></a><span data-ttu-id="6e38f-161">Tupel och avkonstruktion</span><span class="sxs-lookup"><span data-stu-id="6e38f-161">Tuple Deconstruction</span></span>

<span data-ttu-id="6e38f-162">Om den högra sidan av bindningen är en tupel, kan denna tupel bli inbyggd vid tilldelningen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-162">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="6e38f-163">Sådana dekonstruktioner kan omfatta kapslade tupler och all fullständig eller delvis inbyggnad är giltig så länge formen på tuppeln till höger är kompatibel med formen på symbolens tupel.</span><span class="sxs-lookup"><span data-stu-id="6e38f-163">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>
<span data-ttu-id="6e38f-164">Tuple-inkonstruktion kan också användas när den högra sidan av `=` är ett par värdes uttryck.</span><span class="sxs-lookup"><span data-stu-id="6e38f-164">Tuple deconstruction can in particular also be used when the right-hand side of the `=` is a tuple-valued expression.</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a><span data-ttu-id="6e38f-165">Oföränderliga symboler</span><span class="sxs-lookup"><span data-stu-id="6e38f-165">Immutable Symbols</span></span>

<span data-ttu-id="6e38f-166">Oföränderliga symboler binds med hjälp av `let`-instruktionen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-166">Immutable symbols are bound using the `let` statement.</span></span>
<span data-ttu-id="6e38f-167">Detta är ungefär detsamma som variabel deklaration och initiering på språk som C#, förutom att Q #-symboler, när det är kopplat, inte kan ändras. `let` bindningar är oföränderliga.</span><span class="sxs-lookup"><span data-stu-id="6e38f-167">This is roughly equivalent to variable declaration and initialization in languages such as C#, except that Q# symbols, once bound, may not be changed; `let` bindings are immutable.</span></span>

<span data-ttu-id="6e38f-168">En oföränderlig bindning består av nyckelordet `let`följt av en symbol-eller Symbols tupel, ett likhets tecken `=`, ett uttryck för att binda symbolerna till och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="6e38f-168">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="6e38f-169">Typen för den eller de kopplade symbolerna härleds baserat på uttrycket på den högra sidan.</span><span class="sxs-lookup"><span data-stu-id="6e38f-169">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span>

### <a name="mutable-symbols"></a><span data-ttu-id="6e38f-170">Föränderligt symboler</span><span class="sxs-lookup"><span data-stu-id="6e38f-170">Mutable Symbols</span></span>

<span data-ttu-id="6e38f-171">Föränderligt-symboler definieras och initieras med hjälp av `mutable`-instruktionen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-171">Mutable symbols are defined and initialized using the `mutable` statement.</span></span>
<span data-ttu-id="6e38f-172">Symboler som har deklarerats och bundits som en del av en `mutable`-instruktion kan vara kopplade till ett annat värde senare i koden.</span><span class="sxs-lookup"><span data-stu-id="6e38f-172">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> 

<span data-ttu-id="6e38f-173">En föränderligt bindnings instruktion består av nyckelordet `mutable`, följt av en symbol-eller Symbols tupel, ett likhets tecken `=`, ett uttryck för att binda symbolerna till och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="6e38f-173">A mutable binding statement consists of the keyword `mutable`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="6e38f-174">Typen för den eller de kopplade symbolerna härleds baserat på uttrycket på den högra sidan.</span><span class="sxs-lookup"><span data-stu-id="6e38f-174">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span> <span data-ttu-id="6e38f-175">Om en symbol har bundits igen senare i koden, ändras inte dess typ, och det gräns värde som måste vara kompatibelt med den typen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-175">If a symbol is rebound later in the code, its type does not change, and the bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="6e38f-176">OMBINDNING av föränderligt symboler</span><span class="sxs-lookup"><span data-stu-id="6e38f-176">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="6e38f-177">En föränderligt-variabel kan bindas om med hjälp av en `set`-instruktion.</span><span class="sxs-lookup"><span data-stu-id="6e38f-177">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="6e38f-178">En sådan OMBINDNING består av nyckelordet `set`, följt av en symbol-eller Symbols tupel, ett likhets tecken `=`, ett uttryck för att binda om symbolerna till och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="6e38f-178">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="6e38f-179">Värdet måste vara kompatibelt med typ (er) för symbolerna som den är kopplad till.</span><span class="sxs-lookup"><span data-stu-id="6e38f-179">The value must be compatible with the type(s) of the symbol(s) it is bound to.</span></span>

#### <a name="apply-and-reassign-statement"></a><span data-ttu-id="6e38f-180">Instruktionen tillämpa och omtilldela</span><span class="sxs-lookup"><span data-stu-id="6e38f-180">Apply-and-Reassign Statement</span></span>

<span data-ttu-id="6e38f-181">En särskild typ av Set-sats som vi refererar till som en sats för att tillämpa och omtilldela är ett bekvämt sätt att sammanfoga om den högra sidan består av en binär Operators applikation och resultatet måste bindas till det vänstra argumentet till operatorn.</span><span class="sxs-lookup"><span data-stu-id="6e38f-181">A particular kind of set-statement we refer to as an apply-and-reassign statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="6e38f-182">Exempel:</span><span class="sxs-lookup"><span data-stu-id="6e38f-182">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="6e38f-183">ökar värdet för räknaren `counter` i varje iteration av `for`-loopen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-183">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="6e38f-184">Koden ovan motsvarar</span><span class="sxs-lookup"><span data-stu-id="6e38f-184">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
<span data-ttu-id="6e38f-185">Liknande instruktioner är tillgängliga för alla binära operatorer där typen för den vänstra sidan matchar uttrycks typen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-185">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="6e38f-186">Detta ger till exempel ett bekvämt sätt att ackumulera värden:</span><span class="sxs-lookup"><span data-stu-id="6e38f-186">This provides for example a convenient way to accumulate values:</span></span>
```qsharp
mutable results = new Result[0];
for (q in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a><span data-ttu-id="6e38f-187">Instruktionen Uppdatera och omtilldela</span><span class="sxs-lookup"><span data-stu-id="6e38f-187">Update-and-Reassign Statement</span></span>

<span data-ttu-id="6e38f-188">Det finns en liknande sammanfogning för kopiera-och-uppdatera-uttryck på den högra sidan.</span><span class="sxs-lookup"><span data-stu-id="6e38f-188">A similar concatenation exists for copy-and-update expressions on the right hand side.</span></span> <span data-ttu-id="6e38f-189">Det finns ett uttryck för uppdatering och omtilldelning för namngivna objekt i användardefinierade typer samt för mat ris objekt.</span><span class="sxs-lookup"><span data-stu-id="6e38f-189">Correspondingly, update-and-reassign statements exist for named items in user-defined types as well as for array items.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function AddAll (reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="6e38f-190">Om det finns matriser innehåller våra standard bibliotek nödvändiga verktyg för många vanliga behov av initiering och manipulering av matris, och därför kan du undvika att behöva uppdatera mat ris objekt på den första platsen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-190">In the case of arrays, our standard libraries contain the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> <span data-ttu-id="6e38f-191">Uppdaterings-och omtilldelnings instruktioner ger ett alternativ om det behövs:</span><span class="sxs-lookup"><span data-stu-id="6e38f-191">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {

    mutable samples = new Double[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}

operation SampleUniformDistr(nrSamples : Int, prec : Int) : Double[] {

    let normalization = 1. / IntAsDouble(prec);
    mutable samples = RandomInts(prec, nrSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> <span data-ttu-id="6e38f-192">Undvik onödig användning av uppdaterings-och omtilldelnings instruktioner genom att använda de verktyg som finns i <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="6e38f-192">Avoid unnecessary use of update-and-reassign statements by leveraging the tools provided in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="6e38f-193">Funktionen</span><span class="sxs-lookup"><span data-stu-id="6e38f-193">The function</span></span>
```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
{
    mutable pauliArray = new Pauli[n];
    for (index in 0 .. n - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
<span data-ttu-id="6e38f-194">Du kan till exempel enkelt använda funktionen `ConstantArray` i `Microsoft.Quantum.Arrays`och returnera ett kopierings-och-uppdaterings uttryck:</span><span class="sxs-lookup"><span data-stu-id="6e38f-194">for example can simply be simplified using the function `ConstantArray` in `Microsoft.Quantum.Arrays`, and returning a copy-and-update expression:</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    return ConstantArray(n, PauliI) w/ i <- pauli;
}
```

### <a name="binding-scopes"></a><span data-ttu-id="6e38f-195">Bindnings omfång</span><span class="sxs-lookup"><span data-stu-id="6e38f-195">Binding Scopes</span></span>

<span data-ttu-id="6e38f-196">I allmänhet ligger symbol bindningar utanför definitions området och blir instabil i slutet av uttrycks blocket som de inträffar i.</span><span class="sxs-lookup"><span data-stu-id="6e38f-196">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="6e38f-197">Det finns två undantag till den här regeln:</span><span class="sxs-lookup"><span data-stu-id="6e38f-197">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="6e38f-198">Bindningen för loop-variabeln i en `for`-slinga är inom omfånget för for-slingan, men inte efter slutet av slingan.</span><span class="sxs-lookup"><span data-stu-id="6e38f-198">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="6e38f-199">Alla tre delar av en `repeat`/`until` slinga (bröd texten, testet och korrigeringen) behandlas som ett enda omfång, så symboler som är kopplade till bröd texten är tillgängliga i testet och i korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-199">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="6e38f-200">För båda typerna av slingor körs varje steg genom slingan i sin egen omfattning, så bindningar från ett tidigare pass är inte tillgängliga i ett senare pass.</span><span class="sxs-lookup"><span data-stu-id="6e38f-200">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>

<span data-ttu-id="6e38f-201">Symbol bindningar från yttre block ärvs av inre block.</span><span class="sxs-lookup"><span data-stu-id="6e38f-201">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="6e38f-202">En symbol får bara bindas en gång per block. Det är inte tillåtet att definiera en symbol med samma namn som en annan symbol inom omfånget (ingen "skuggning").</span><span class="sxs-lookup"><span data-stu-id="6e38f-202">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="6e38f-203">Följande sekvenser är juridiska:</span><span class="sxs-lookup"><span data-stu-id="6e38f-203">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="6e38f-204">och</span><span class="sxs-lookup"><span data-stu-id="6e38f-204">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
```

<span data-ttu-id="6e38f-205">Men detta skulle vara ogiltigt:</span><span class="sxs-lookup"><span data-stu-id="6e38f-205">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="6e38f-206">som skulle:</span><span class="sxs-lookup"><span data-stu-id="6e38f-206">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a><span data-ttu-id="6e38f-207">Kontrollflöde</span><span class="sxs-lookup"><span data-stu-id="6e38f-207">Control Flow</span></span>

### <a name="for-loop"></a><span data-ttu-id="6e38f-208">For-slinga</span><span class="sxs-lookup"><span data-stu-id="6e38f-208">For Loop</span></span>

<span data-ttu-id="6e38f-209">Instruktionen `for` stöder iteration över ett heltals intervall eller över en matris.</span><span class="sxs-lookup"><span data-stu-id="6e38f-209">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="6e38f-210">Instruktionen består av nyckelordet `for`, en öppen parentes `(`följt av en symbol eller symbol tupel, nyckelordet `in`, ett uttryck av typen `Range` eller matris, en avslutande parentes `)`och ett instruktions block.</span><span class="sxs-lookup"><span data-stu-id="6e38f-210">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="6e38f-211">Instruktions blocket (bröd texten i slingan) körs upprepade gånger, med de definierade symbolerna (loop-variabeln) som är kopplade till varje värde i intervallet eller matrisen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-211">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="6e38f-212">Observera att om intervall uttrycket utvärderas till ett tomt intervall eller en matris, körs inte bröd texten alls.</span><span class="sxs-lookup"><span data-stu-id="6e38f-212">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="6e38f-213">Uttrycket utvärderas fullständigt innan det går in i loopen och ändras inte när slingan körs.</span><span class="sxs-lookup"><span data-stu-id="6e38f-213">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="6e38f-214">Bindningen för de deklarerade symbolerna är oföränderlig och följer samma regler som andra variabel bindningar.</span><span class="sxs-lookup"><span data-stu-id="6e38f-214">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> <span data-ttu-id="6e38f-215">I synnerhet är det möjligt att Destruct, t. ex. mat ris objekt för en iteration över en matris vid tilldelning till loop-variabeln (s).</span><span class="sxs-lookup"><span data-stu-id="6e38f-215">In particular, it is possible to destruct e.g. array items for an iteration over an array upon assignment to the loop variable(s).</span></span>

<span data-ttu-id="6e38f-216">Exempel:</span><span class="sxs-lookup"><span data-stu-id="6e38f-216">For example,</span></span>

```qsharp
// ...
for (qb in qubits) { // qubits contains a Qubit[]
    H(qb);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="6e38f-217">Loop-variabeln binds vid varje ingång till loop-texten och är obunden i slutet av bröd texten.</span><span class="sxs-lookup"><span data-stu-id="6e38f-217">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="6e38f-218">I synnerhet är loop-variabeln inte kopplad efter att for-slingan har slutförts.</span><span class="sxs-lookup"><span data-stu-id="6e38f-218">In particular, the loop variable is not bound after the for loop is completed.</span></span>

### <a name="repeat-until-success-loop"></a><span data-ttu-id="6e38f-219">Upprepa-tills-lyckad-slinga</span><span class="sxs-lookup"><span data-stu-id="6e38f-219">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="6e38f-220">Instruktionen `repeat` stöder Quantum-mönstret "Upprepa tills lyckat".</span><span class="sxs-lookup"><span data-stu-id="6e38f-220">The `repeat` statement supports the quantum “repeat until success” pattern.</span></span>
<span data-ttu-id="6e38f-221">Det består av nyckelordet `repeat`följt av ett instruktions block ( _loop_ -texten), nyckelordet `until`, ett booleskt uttryck och antingen ett avslutande semikolon eller nyckelordet `fixup` följt av ett annat instruktions block ( _korrigeringen_).</span><span class="sxs-lookup"><span data-stu-id="6e38f-221">It consists of the keyword `repeat`, followed by a statement block (the _loop_ body), the keyword `until`, a Boolean expression, and either a terminating semicolon or the keyword `fixup` followed by another statement block (the _fixup_).</span></span>
<span data-ttu-id="6e38f-222">Loop-texten, villkoret och korrigeringen betraktas som alla som ett enda omfång, så symboler som är kopplade till texten är tillgängliga i villkoret och korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-222">The loop body, condition, and fixup are all considered to be a single scope, so symbols bound in the body are available in the condition and fixup.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qs);
    let success = ComputeSuccessIndicator(qs);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qs);
}
```

<span data-ttu-id="6e38f-223">Loop-texten körs och sedan utvärderas villkoret.</span><span class="sxs-lookup"><span data-stu-id="6e38f-223">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="6e38f-224">Om villkoret är sant slutförs instruktionen. annars utförs korrigeringen och instruktionen körs igen från och med loop-texten.</span><span class="sxs-lookup"><span data-stu-id="6e38f-224">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>
<span data-ttu-id="6e38f-225">Observera att om du slutför körningen av korrigeringen avslutas omfånget för instruktionen, så att symbol bindningar som görs under bröd texten eller korrigeringen inte är tillgängliga i efterföljande upprepningar.</span><span class="sxs-lookup"><span data-stu-id="6e38f-225">Note that completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="6e38f-226">Följande kod är till exempel en Probabilistic-krets som implementerar en viktig rotations grind $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ med Hadamard-och T-grindarna.</span><span class="sxs-lookup"><span data-stu-id="6e38f-226">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the Hadamard and T gates.</span></span>
<span data-ttu-id="6e38f-227">Slingan upphör om 8/5 upprepningar i genomsnitt.</span><span class="sxs-lookup"><span data-stu-id="6e38f-227">The loop terminates in 8/5 repetitions on average.</span></span>
<span data-ttu-id="6e38f-228">Se [*REPEAT-until-lyckades: icke-deterministisk dekomposition av Single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick och Svore, 2014) för mer information.</span><span class="sxs-lookup"><span data-stu-id="6e38f-228">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for details.</span></span>

```qsharp
using (anc = Qubit()) {
    repeat {
        H(anc);
        T(anc);
        CNOT(target,anc);
        H(anc);
        Adjoint T(anc);
        H(anc);
        T(anc);
        H(anc);
        CNOT(target,anc);
        T(anc);
        Z(target);
        H(anc);
        let result = M(anc);
    } until (result == Zero);
}
```

> [!TIP]   
> <span data-ttu-id="6e38f-229">Undvik att använda repetitions-till-Slutför-slingor inuti functions.</span><span class="sxs-lookup"><span data-stu-id="6e38f-229">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="6e38f-230">Motsvarande funktioner tillhandahålls av while-slingor i functions.</span><span class="sxs-lookup"><span data-stu-id="6e38f-230">The corresponding functionality is provided by while loops in functions.</span></span> 

### <a name="while-loop"></a><span data-ttu-id="6e38f-231">While-slinga</span><span class="sxs-lookup"><span data-stu-id="6e38f-231">While Loop</span></span>

<span data-ttu-id="6e38f-232">Upprepa-tills-lyckad-mönster har en mycket Quantum-speciell connotation.</span><span class="sxs-lookup"><span data-stu-id="6e38f-232">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="6e38f-233">De används ofta i vissa klasser av Quantum-algoritmer – därför är den dedikerade språk konstruktionen i Q #.</span><span class="sxs-lookup"><span data-stu-id="6e38f-233">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="6e38f-234">Loopar som bryts baserat på ett villkor och vars körnings längd alltså är okänd vid kompileringen måste dock hanteras med särskild försiktighet i en Quantum-körning.</span><span class="sxs-lookup"><span data-stu-id="6e38f-234">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="6e38f-235">Deras användning i functions å andra sidan är problematisk, eftersom dessa endast innehåller kod som ska köras på konventionell (icke-Quantum) maskin vara.</span><span class="sxs-lookup"><span data-stu-id="6e38f-235">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="6e38f-236">Q # stöder därför endast användningen av while-slingor i functions.</span><span class="sxs-lookup"><span data-stu-id="6e38f-236">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="6e38f-237">En `while`-instruktion består av nyckelordet `while`, en öppen parentes `(`, ett villkor (t. ex. ett booleskt uttryck), en avslutande parentes `)`och ett instruktions block.</span><span class="sxs-lookup"><span data-stu-id="6e38f-237">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="6e38f-238">Instruktions blocket (bröd texten i slingan) körs så länge villkoret utvärderas till `true`.</span><span class="sxs-lookup"><span data-stu-id="6e38f-238">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a><span data-ttu-id="6e38f-239">Villkors instruktion</span><span class="sxs-lookup"><span data-stu-id="6e38f-239">Conditional Statement</span></span>

<span data-ttu-id="6e38f-240">Instruktionen `if` stöder villkorlig körning.</span><span class="sxs-lookup"><span data-stu-id="6e38f-240">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="6e38f-241">Det består av nyckelordet `if`, en öppen parentes `(`, ett booleskt uttryck, en avslutande parentes `)`och ett instruktions block ( _then_ -block).</span><span class="sxs-lookup"><span data-stu-id="6e38f-241">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="6e38f-242">Detta kan följas av valfri mängd Else-If-satser, som består av nyckelordet `elif`, en öppen parentes `(`, ett booleskt uttryck, en högerparentes `)`och ett instruktions block ( _Else-If-_ block).</span><span class="sxs-lookup"><span data-stu-id="6e38f-242">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="6e38f-243">Slutligen kan instruktionen avslutas med en Else-sats som består av nyckelordet `else` följt av ett annat instruktions block ( _Else_ -blocket).</span><span class="sxs-lookup"><span data-stu-id="6e38f-243">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>
<span data-ttu-id="6e38f-244">Villkoret utvärderas och om det är sant körs blocket.</span><span class="sxs-lookup"><span data-stu-id="6e38f-244">The condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="6e38f-245">Om villkoret är falskt utvärderas det första Else-If-villkoret. om det är sant körs det Else-If-blocket.</span><span class="sxs-lookup"><span data-stu-id="6e38f-245">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="6e38f-246">Annars testas det andra-IF-blocket, och sedan den tredje, och så vidare tills en sats med ett True-villkor påträffas eller det inte finns några Else If-satser.</span><span class="sxs-lookup"><span data-stu-id="6e38f-246">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="6e38f-247">Om det ursprungliga IF-villkoret och alla Else-If-satser utvärderas till false körs Else-blocket om ett har angetts.</span><span class="sxs-lookup"><span data-stu-id="6e38f-247">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="6e38f-248">Observera att det körs på det egna omfånget.</span><span class="sxs-lookup"><span data-stu-id="6e38f-248">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="6e38f-249">Bindningar som görs inuti ett then-, Else-If-eller Else-block visas inte efter slutet av IF-instruktionen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-249">Bindings made inside of a then, else-if, or else block are not visible after the end of the if statement.</span></span>

<span data-ttu-id="6e38f-250">Exempel:</span><span class="sxs-lookup"><span data-stu-id="6e38f-250">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
} 
```

<span data-ttu-id="6e38f-251">eller</span><span class="sxs-lookup"><span data-stu-id="6e38f-251">or</span></span>

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a><span data-ttu-id="6e38f-252">returrelaterade</span><span class="sxs-lookup"><span data-stu-id="6e38f-252">Return</span></span>

<span data-ttu-id="6e38f-253">Return-instruktionen avslutar körningen av en åtgärd eller funktion och returnerar ett värde till anroparen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-253">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="6e38f-254">Det består av nyckelordet `return`följt av ett uttryck av lämplig typ och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="6e38f-254">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="6e38f-255">Ett anrop som returnerar en tom tupel, `()`, kräver ingen Return-instruktion.</span><span class="sxs-lookup"><span data-stu-id="6e38f-255">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="6e38f-256">Om en tidig avslutning önskas kan `return ()` användas i det här fallet.</span><span class="sxs-lookup"><span data-stu-id="6e38f-256">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="6e38f-257">Callables som returnerar någon annan typ kräver en slutgiltig Return-instruktion.</span><span class="sxs-lookup"><span data-stu-id="6e38f-257">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="6e38f-258">Det finns inget maximalt antal retur uttryck i en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="6e38f-258">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="6e38f-259">Kompilatorn kan generera en varning om instruktioner följer en Return-instruktion i ett block.</span><span class="sxs-lookup"><span data-stu-id="6e38f-259">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="6e38f-260">Exempel:</span><span class="sxs-lookup"><span data-stu-id="6e38f-260">For example,</span></span>

```qsharp
return 1;
```

<span data-ttu-id="6e38f-261">eller</span><span class="sxs-lookup"><span data-stu-id="6e38f-261">or</span></span>

```qsharp
return ();
```

<span data-ttu-id="6e38f-262">eller</span><span class="sxs-lookup"><span data-stu-id="6e38f-262">or</span></span>

```qsharp
return (results, qubits);
```

### <a name="fail"></a><span data-ttu-id="6e38f-263">Kanske</span><span class="sxs-lookup"><span data-stu-id="6e38f-263">Fail</span></span>

<span data-ttu-id="6e38f-264">Instruktionen Error avslutar körningen av en åtgärd och returnerar ett felvärde till anroparen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-264">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="6e38f-265">Det består av nyckelordet `fail`följt av en sträng och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="6e38f-265">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="6e38f-266">Strängen returneras till den klassiska driv rutinen som fel meddelande.</span><span class="sxs-lookup"><span data-stu-id="6e38f-266">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="6e38f-267">Det finns ingen begränsning för antalet misslyckande uttryck i en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="6e38f-267">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="6e38f-268">Kompilatorn kan generera en varning om instruktioner följer en felaktig instruktion i ett block.</span><span class="sxs-lookup"><span data-stu-id="6e38f-268">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="6e38f-269">Exempel:</span><span class="sxs-lookup"><span data-stu-id="6e38f-269">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```

<span data-ttu-id="6e38f-270">eller</span><span class="sxs-lookup"><span data-stu-id="6e38f-270">or</span></span>

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a><span data-ttu-id="6e38f-271">Hantering av qubit</span><span class="sxs-lookup"><span data-stu-id="6e38f-271">Qubit Management</span></span>

<span data-ttu-id="6e38f-272">Observera att ingen av dessa instruktioner tillåts i bröd texten i en funktion.</span><span class="sxs-lookup"><span data-stu-id="6e38f-272">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="6e38f-273">De är endast giltiga inom åtgärder.</span><span class="sxs-lookup"><span data-stu-id="6e38f-273">They are only valid within operations.</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="6e38f-274">Rengör qubits</span><span class="sxs-lookup"><span data-stu-id="6e38f-274">Clean Qubits</span></span>

<span data-ttu-id="6e38f-275">Instruktionen `using` används för att hämta nya qubits för användning under ett instruktions block.</span><span class="sxs-lookup"><span data-stu-id="6e38f-275">The `using` statement is used to acquire new qubits for use during a statement block.</span></span>
<span data-ttu-id="6e38f-276">Qubits är garanterat att initieras till beräknings `Zero`s tillstånd.</span><span class="sxs-lookup"><span data-stu-id="6e38f-276">The qubits are guaranteed to be initialized to the computational `Zero` state.</span></span>
<span data-ttu-id="6e38f-277">Qubits ska vara i beräknings `Zero`s tillstånd i slutet av instruktions blocket. simulatorer uppmuntras att genomdriva detta.</span><span class="sxs-lookup"><span data-stu-id="6e38f-277">The qubits should be in the computational `Zero` state at the end of the statement block; simulators are encouraged to enforce this.</span></span>

<span data-ttu-id="6e38f-278">Instruktionen består av nyckelordet `using`följt av en öppen parentes `(`, en bindning, en avslutande parentes `)`och instruktions blocket som qubits är tillgängligt i.</span><span class="sxs-lookup"><span data-stu-id="6e38f-278">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="6e38f-279">Bindningen följer samma mönster som `let`-satser: antingen en symbol eller en tupel med symboler, följt av ett likhets tecken `=`, och antingen ett enda värde eller en matchande tupel av initierare.</span><span class="sxs-lookup"><span data-stu-id="6e38f-279">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of initializers.</span></span>
<span data-ttu-id="6e38f-280">Initierare är tillgängliga antingen för en enskild qubit, anges som `Qubit()`eller en matris med qubits, som anges av `Qubit[`, ett `Int` uttryck och `]`.</span><span class="sxs-lookup"><span data-stu-id="6e38f-280">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, indicated by `Qubit[`, an `Int` expression, and `]`.</span></span>

<span data-ttu-id="6e38f-281">Exempel:</span><span class="sxs-lookup"><span data-stu-id="6e38f-281">For example,</span></span>

```qsharp
using (q = Qubit()) {
    // ...
}
using ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="dirty-qubits"></a><span data-ttu-id="6e38f-282">Smutsig qubits</span><span class="sxs-lookup"><span data-stu-id="6e38f-282">Dirty Qubits</span></span>

<span data-ttu-id="6e38f-283">`borrowing`-instruktionen används för att hämta qubits för tillfällig användning.</span><span class="sxs-lookup"><span data-stu-id="6e38f-283">The `borrowing` statement is used to obtain qubits for temporary use.</span></span> <span data-ttu-id="6e38f-284">Instruktionen består av nyckelordet `borrowing`följt av en öppen parentes `(`, en bindning, en avslutande parentes `)`och instruktions blocket som qubits är tillgängligt i.</span><span class="sxs-lookup"><span data-stu-id="6e38f-284">The statement consists of the keyword `borrowing`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="6e38f-285">Bindningen följer samma mönster och regler som i en `using`-instruktion.</span><span class="sxs-lookup"><span data-stu-id="6e38f-285">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>

<span data-ttu-id="6e38f-286">Exempel:</span><span class="sxs-lookup"><span data-stu-id="6e38f-286">For example,</span></span>

```qsharp
borrowing (q = Qubit()) {
    // ...
}
borrowing ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

<span data-ttu-id="6e38f-287">De lånade qubits är i ett okänt tillstånd och hamnar utanför definitions området i slutet av instruktions blocket.</span><span class="sxs-lookup"><span data-stu-id="6e38f-287">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="6e38f-288">Låntagaren åtar sig att lämna qubits i samma tillstånd som de var i när de lånades, d.v.s. deras tillstånd i början och i slutet av instruktions blocket förväntas vara detsamma.</span><span class="sxs-lookup"><span data-stu-id="6e38f-288">The borrower commits to leaving the qubits in the same state they were in when they were borrowed, i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="6e38f-289">Detta tillstånd är i synnerhet inte nödvändigt vis ett klassiskt läge, som i de flesta fall bör låne omfång inte innehålla mätningar.</span><span class="sxs-lookup"><span data-stu-id="6e38f-289">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="6e38f-290">Sådana qubits kallas ofta "smutsig Ancilla".</span><span class="sxs-lookup"><span data-stu-id="6e38f-290">Such qubits are often known as “dirty ancilla”.</span></span>
<span data-ttu-id="6e38f-291">Se [*factoring med hjälp av 2n + 2 qubits med Toffoli-baserad modulär multiplikation*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler och Svore 2017) för ett exempel på smutsig Ancilla användning.</span><span class="sxs-lookup"><span data-stu-id="6e38f-291">See [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an example of dirty ancilla use.</span></span>

<span data-ttu-id="6e38f-292">När du lånar qubits försöker systemet först att fylla i begäran från qubits som används men som inte har öppnats under bröd texten i `borrowing`-instruktionen.</span><span class="sxs-lookup"><span data-stu-id="6e38f-292">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="6e38f-293">Om det inte finns tillräckligt med sådan qubits, kommer den att allokera nya qubits för att slutföra begäran.</span><span class="sxs-lookup"><span data-stu-id="6e38f-293">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>

## <a name="conjugations"></a><span data-ttu-id="6e38f-294">Conjugations</span><span class="sxs-lookup"><span data-stu-id="6e38f-294">Conjugations</span></span>

<span data-ttu-id="6e38f-295">Till skillnad från klassiska bitar är det något mer engagerande att frigöra Quantum-minne eftersom qubits kan ha oönskade effekter på den återstående beräkningen om qubits fortfarande är Entangled.</span><span class="sxs-lookup"><span data-stu-id="6e38f-295">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="6e38f-296">Detta kan undvikas genom att du avregistrerar utförda beräkningar innan du frigör minnet.</span><span class="sxs-lookup"><span data-stu-id="6e38f-296">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="6e38f-297">Ett vanligt mönster i Quantum Computing är därför följande:</span><span class="sxs-lookup"><span data-stu-id="6e38f-297">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="6e38f-298">: nytt: från och med vår 0,9-utgåva har vi stöd för en conjugation-instruktion som implementerar omvandlingen ovan.</span><span class="sxs-lookup"><span data-stu-id="6e38f-298">:new: Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="6e38f-299">Med den här instruktionen kan åtgärds `ApplyWith` implementeras på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="6e38f-299">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="6e38f-300">En sådan conjugation-instruktion är självklart mycket mer användbar om den yttre och inre omvandlingen inte är tillgänglig som åtgärder, men är i stället bekvämare att beskriva genom ett block som består av flera instruktioner.</span><span class="sxs-lookup"><span data-stu-id="6e38f-300">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="6e38f-301">Den inverterade omvandlingen för de instruktioner som definierats inom blocket genereras automatiskt av kompileraren och körs när Apply-blocket har slutförts.</span><span class="sxs-lookup"><span data-stu-id="6e38f-301">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span> <span data-ttu-id="6e38f-302">Eftersom alla föränderligt-variabler som används som en del av inom-blocket inte kan bindas om i Apply-blocket, garanteras den genererade omvandlingen som det angränsande av beräkningen i avsnittet-block.</span><span class="sxs-lookup"><span data-stu-id="6e38f-302">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="expression-evaluation-statements"></a><span data-ttu-id="6e38f-303">Utvärderings satser för uttryck</span><span class="sxs-lookup"><span data-stu-id="6e38f-303">Expression Evaluation Statements</span></span>

<span data-ttu-id="6e38f-304">Ett anrops uttryck av typen `Unit` kan användas som en instruktion.</span><span class="sxs-lookup"><span data-stu-id="6e38f-304">Any call expression of type `Unit` may be used as a statement.</span></span>
<span data-ttu-id="6e38f-305">Detta används främst för att anropa åtgärder på qubits som returnerar `Unit` eftersom syftet med instruktionen är att ändra implicit Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="6e38f-305">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="6e38f-306">Uttrycks utvärderings uttryck kräver ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="6e38f-306">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="6e38f-307">Exempel:</span><span class="sxs-lookup"><span data-stu-id="6e38f-307">For example,</span></span>

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
