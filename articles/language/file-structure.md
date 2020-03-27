---
title: 'Q # fil struktur'
description: 'Lär dig hur du strukturerar namn områden och åtgärder, funktioner och användardefinierade deklarationer i Q #-program och-bibliotek.'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 96de062bc6ce4edf94520bec449e8d95259c0f5c
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320768"
---
# <a name="file-structure"></a><span data-ttu-id="d6061-103">Filstruktur</span><span class="sxs-lookup"><span data-stu-id="d6061-103">File Structure</span></span>

<span data-ttu-id="d6061-104">En Q #-fil består av en sekvens med namn områdes deklarationer.</span><span class="sxs-lookup"><span data-stu-id="d6061-104">A Q# file consists of a sequence of namespace declarations.</span></span>
<span data-ttu-id="d6061-105">Varje namn områdes deklaration innehåller deklarationer för användardefinierade typer, åtgärder och funktioner.</span><span class="sxs-lookup"><span data-stu-id="d6061-105">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="d6061-106">En namn områdes deklaration får innehålla valfritt antal av varje typ av deklaration, och i vilken ordning som helst.</span><span class="sxs-lookup"><span data-stu-id="d6061-106">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="d6061-107">Den enda text som kan visas utanför en namn områdes deklaration är kommentarer.</span><span class="sxs-lookup"><span data-stu-id="d6061-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="d6061-108">I synnerhet är dokumentations kommentarer för ett namn område före deklarationen.</span><span class="sxs-lookup"><span data-stu-id="d6061-108">In particular, documentation comments for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="d6061-109">Namn områdes deklarationer</span><span class="sxs-lookup"><span data-stu-id="d6061-109">Namespace Declarations</span></span>

<span data-ttu-id="d6061-110">En Q #-fil har vanligt vis exakt en namn områdes deklaration, men kan ha ingen (och vara tom eller bara innehålla kommentarer) eller innehålla flera namn områden.</span><span class="sxs-lookup"><span data-stu-id="d6061-110">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="d6061-111">Namespace-deklarationer får inte vara kapslade.</span><span class="sxs-lookup"><span data-stu-id="d6061-111">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="d6061-112">Samma namnrymd kan deklareras i flera Q #-filer som kompileras tillsammans, så länge det inte finns någon typ, åtgärd eller funktions deklaration med samma namn.</span><span class="sxs-lookup"><span data-stu-id="d6061-112">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="d6061-113">I synnerhet är det inte tillåtet att definiera samma typ i samma namnrymd i flera filer, även om deklarationerna är identiska.</span><span class="sxs-lookup"><span data-stu-id="d6061-113">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="d6061-114">En namn områdes deklaration består av nyckelordet `namespace`följt av namnet på namn området, en öppen klammerparentes `{`, de deklarationer som finns i namn området och en avslutande klammerparentes `}`.</span><span class="sxs-lookup"><span data-stu-id="d6061-114">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="d6061-115">Namn områdes namn följer .NET-mönstret för en sekvens med en eller flera juridiska symboler avgränsade med punkter `.`.</span><span class="sxs-lookup"><span data-stu-id="d6061-115">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="d6061-116">`MyQuantumStuff` och `Microsoft.Quantum.Canon` är till exempel giltiga namn rymds namn.</span><span class="sxs-lookup"><span data-stu-id="d6061-116">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Canon` are valid namespace names.</span></span>
<span data-ttu-id="d6061-117">Enligt konvention är symbolerna i namn områdes namnet versaler, men det är inget krav.</span><span class="sxs-lookup"><span data-stu-id="d6061-117">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="d6061-118">Deklarationer kan visas i valfri ordning i en namn områdes deklaration.</span><span class="sxs-lookup"><span data-stu-id="d6061-118">Declarations may appear in any order in a namespace declaration.</span></span>
<span data-ttu-id="d6061-119">Referenser till typer eller callables som deklarerats senare i en fil löses korrekt. Det finns inget behov av typen, åtgärden eller funktions deklarationen att föregå en referens till den.</span><span class="sxs-lookup"><span data-stu-id="d6061-119">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="d6061-120">Öppna direktiv</span><span class="sxs-lookup"><span data-stu-id="d6061-120">Open Directives</span></span>

<span data-ttu-id="d6061-121">I ett namn områdes block kan `open`-direktivet användas för att importera alla typer och callables som definierats i ett visst namn område och referera till dem med hjälp av okvalificerade namn.</span><span class="sxs-lookup"><span data-stu-id="d6061-121">Within a namespace block, the `open` directive may be used to import all types and callables defined in a certain namespace and refer to them by their unqualified name.</span></span> 

<span data-ttu-id="d6061-122">Ett sådant `open`-direktiv består av `open` nyckelord, följt av namn området som ska öppnas och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="d6061-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

<span data-ttu-id="d6061-123">Till exempel,</span><span class="sxs-lookup"><span data-stu-id="d6061-123">For instance,</span></span>

```qsharp
open Microsoft.Quantum.Canon;
```

<span data-ttu-id="d6061-124">Alternativt kan ett kort namn för det öppna namn området definieras så att alla element från det namn området kan (och behöver) kvalificeras av det definierade korta namnet.</span><span class="sxs-lookup"><span data-stu-id="d6061-124">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="d6061-125">Ett sådant kort namn definieras genom att nyckelordet läggs `as` följt av det önskade korta namnet före semikolonet i ett `open`-direktiv:</span><span class="sxs-lookup"><span data-stu-id="d6061-125">Such a short name is defined by adding the keyword `as` followed by the desired short name before the semicolon in an `open` directive:</span></span>

```qsharp
open Microsoft.Quantum.Math as Math;
```

<span data-ttu-id="d6061-126">Alla `open`-direktiv måste finnas före eventuella `function`-, `operation`-eller `newtype`-deklarationer i namn områdes blocket.</span><span class="sxs-lookup"><span data-stu-id="d6061-126">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>
<span data-ttu-id="d6061-127">`open`-direktivet gäller hela namn områdes blocket i en fil.</span><span class="sxs-lookup"><span data-stu-id="d6061-127">The `open` directive applies to the entire namespace block within a file.</span></span>

## <a name="user-defined-type-declarations"></a><span data-ttu-id="d6061-128">Användardefinierade typ deklarationer</span><span class="sxs-lookup"><span data-stu-id="d6061-128">User-Defined Type Declarations</span></span>

<span data-ttu-id="d6061-129">Q # gör det möjligt för användare att deklarera nya användardefinierade typer, enligt beskrivningen i avsnittet om [typ modell för Q](xref:microsoft.quantum.language.type-model) .</span><span class="sxs-lookup"><span data-stu-id="d6061-129">Q# provides a way for users to declare new user-defined types, as described in the [Q# type model](xref:microsoft.quantum.language.type-model) section.</span></span>
<span data-ttu-id="d6061-130">Användardefinierade typer är distinkta även om bas typerna är identiska.</span><span class="sxs-lookup"><span data-stu-id="d6061-130">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="d6061-131">I synnerhet finns det ingen automatisk konvertering mellan värden av två användardefinierade typer, även om de underliggande typerna är identiska.</span><span class="sxs-lookup"><span data-stu-id="d6061-131">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

<span data-ttu-id="d6061-132">En användardefinierad typ deklaration består av nyckelordet `newtype`följt av namnet på den användardefinierade typen, en `=`, en giltig typ specifikation och ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="d6061-132">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="d6061-133">Några exempel:</span><span class="sxs-lookup"><span data-stu-id="d6061-133">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="d6061-134">Varje Q #-källfil kan deklarera ett valfritt antal användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="d6061-134">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="d6061-135">Typnamn måste vara unika inom ett namn område och kan inte vara i konflikt med funktions-och funktions namn.</span><span class="sxs-lookup"><span data-stu-id="d6061-135">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="d6061-136">Det går inte att definiera cirkulära beroenden mellan användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="d6061-136">It is not possible to define circular dependencies between user defined types.</span></span> <span data-ttu-id="d6061-137">Rekursiva typer är därför inte möjliga inom Q #.</span><span class="sxs-lookup"><span data-stu-id="d6061-137">Recursive types are thus not possible within Q#.</span></span>

## <a name="operation-declarations"></a><span data-ttu-id="d6061-138">Åtgärds deklarationer</span><span class="sxs-lookup"><span data-stu-id="d6061-138">Operation Declarations</span></span>

<span data-ttu-id="d6061-139">Åtgärder är kärnan i Q #, ungefär likvärdiga med funktioner på andra språk.</span><span class="sxs-lookup"><span data-stu-id="d6061-139">Operations are the core of Q#, roughly analogous to functions in other languages.</span></span>
<span data-ttu-id="d6061-140">Varje Q #-källfil kan definiera valfritt antal åtgärder.</span><span class="sxs-lookup"><span data-stu-id="d6061-140">Each Q# source file may define any number of operations.</span></span>

<span data-ttu-id="d6061-141">Åtgärds namn måste vara unika inom ett namn område och får inte stå i konflikt med typ-och funktions namn.</span><span class="sxs-lookup"><span data-stu-id="d6061-141">Operation names must be unique within a namespace and may not conflict with type and function names.</span></span>

<span data-ttu-id="d6061-142">En åtgärds deklaration består av nyckelordet `operation`, följt av symbolen som är åtgärdens namn, en typ av identifierare som definierar argumenten för åtgärden, ett kolon `:`, en typ anteckning som beskriver åtgärdens resultat typ, eventuellt en anteckning med åtgärds egenskaper, en öppen klammer `{`, bröd texten i åtgärds deklarationen och en avslutande klammerparentes `}`.</span><span class="sxs-lookup"><span data-stu-id="d6061-142">An operation declarations consists of the keyword `operation`, followed by the symbol that is the operation’s name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation’s result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="d6061-143">Bröd texten i åtgärds deklarationen består antingen av standard implementeringen eller en lista över specialiseringar.</span><span class="sxs-lookup"><span data-stu-id="d6061-143">The body of the operation declaration either consists of the default implementation or of a list of specializations.</span></span>
<span data-ttu-id="d6061-144">Standard implementeringen kan anges direkt i deklarationen om endast implementeringen av standard-specialisering måste anges explicit.</span><span class="sxs-lookup"><span data-stu-id="d6061-144">The default implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to specified explicitly.</span></span>
<span data-ttu-id="d6061-145">I det här fallet är en anteckning med åtgärds egenskaperna i deklarationen användbar för att säkerställa att kompileraren automatiskt genererar andra specialiseringar baserat på standard implementeringen.</span><span class="sxs-lookup"><span data-stu-id="d6061-145">In this case, an annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="d6061-146">Exempel</span><span class="sxs-lookup"><span data-stu-id="d6061-146">For example</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

<span data-ttu-id="d6061-147">Åtgärds egenskaper definierar vilka typer av functors som kan tillämpas på den deklarerade åtgärden och vilken effekt de har.</span><span class="sxs-lookup"><span data-stu-id="d6061-147">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="d6061-148">Om en åtgärd implementerar en enhetlig omvandling, är det möjligt att definiera hur åtgärden fungerar när *adjointed* eller *kontrol leras*.</span><span class="sxs-lookup"><span data-stu-id="d6061-148">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span>
<span data-ttu-id="d6061-149">Förekomsten av dessa specialiseringar kan deklareras som en del av åtgärdens signatur.</span><span class="sxs-lookup"><span data-stu-id="d6061-149">The existence of these specializations can be declared as part of the operation signature.</span></span> <span data-ttu-id="d6061-150">Motsvarande implementering för varje sådan implicit deklarerad specialisering genereras sedan av kompileraren.</span><span class="sxs-lookup"><span data-stu-id="d6061-150">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> <span data-ttu-id="d6061-151">I exemplet ovan genereras ett intilliggande, en styrd och en kontrollerad angränsande specialisering av kompileraren.</span><span class="sxs-lookup"><span data-stu-id="d6061-151">In the example above, an adjoint, a controlled, and a controlled adjoint specialization are generated by the compiler.</span></span> 

<span data-ttu-id="d6061-152">Om implementeringen inte kan genereras av kompilatorn kan den uttryckligen anges.</span><span class="sxs-lookup"><span data-stu-id="d6061-152">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="d6061-153">Sådana uttryckliga specialiserings deklarationer kan antingen bestå av ett lämpligt generations direktiv som klargör hur en viss specialisering ska skapas eller en användardefinierad implementering.</span><span class="sxs-lookup"><span data-stu-id="d6061-153">Such explicit specialization declarations can either consist of a suitable generation directive that clarify how a certain specialization is to be built, or a user defined implementation.</span></span> <span data-ttu-id="d6061-154">Koden i `PrepareEntangledPair` ovan motsvarar exempelvis koden nedan som innehåller explicita specialiserings deklarationer:</span><span class="sxs-lookup"><span data-stu-id="d6061-154">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="d6061-155">Nyckelordet `auto` anger att kompilatorn ska fastställa hur specialiserings implementeringen ska genereras.</span><span class="sxs-lookup"><span data-stu-id="d6061-155">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="d6061-156">Om kompilatorn inte kan generera implementeringen för en viss specialisering utan ytterligare instruktioner, som ett mer exakt generations direktiv, eller om en effektivare implementering kan ges, kan implementeringen också definieras manuellt.</span><span class="sxs-lookup"><span data-stu-id="d6061-156">If the compiler cannot generate the implementation for a certain specialization without further instructions - like a more precise generation directive -, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```

<span data-ttu-id="d6061-157">I exemplet ovan anger `adjoint invert;` att den angränsande specialiseringen ska genereras genom att invertera bröd texten och `controlled adjoint invert;` anger att den kontrollerade intilliggande specialiseringen ska genereras genom att den angivna implementeringen av den kontrollerade specialiseringen inverteras.</span><span class="sxs-lookup"><span data-stu-id="d6061-157">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="d6061-158">För att en åtgärd ska kunna stödja program av `Adjoint` och/eller `Controlled` Functor måste dess returtyp nödvändigt vis `Unit`.</span><span class="sxs-lookup"><span data-stu-id="d6061-158">For an operation to support application of the `Adjoint` and/or `Controlled` functor, its return type necessarily needs to be `Unit`.</span></span> 


### <a name="explicit-specialization-declarations"></a><span data-ttu-id="d6061-159">Explicita specialiserings deklarationer</span><span class="sxs-lookup"><span data-stu-id="d6061-159">Explicit Specialization Declarations</span></span>

<span data-ttu-id="d6061-160">Q #-åtgärder kan innehålla följande uttryckliga specialiserings deklarationer:</span><span class="sxs-lookup"><span data-stu-id="d6061-160">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="d6061-161">`body` specialisering anger implementeringen av åtgärden utan att functors tillämpas.</span><span class="sxs-lookup"><span data-stu-id="d6061-161">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="d6061-162">`adjoint` specialisering anger implementeringen av åtgärden med den `Adjoint` Functor som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="d6061-162">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="d6061-163">`controlled` specialisering anger implementeringen av åtgärden med den `Controlled` Functor som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="d6061-163">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="d6061-164">`controlled adjoint` specialisering anger implementeringen av åtgärden med både `Adjoint` och `Controlled` functors tillämpas.</span><span class="sxs-lookup"><span data-stu-id="d6061-164">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="d6061-165">Den här specialiseringen kan också ha namnet `adjoint controlled`, eftersom de två functorsna går på distans.</span><span class="sxs-lookup"><span data-stu-id="d6061-165">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="d6061-166">En åtgärds-specialisering består av en specialisering (t. ex. `body`eller `adjoint`osv.) följt av någon av följande:</span><span class="sxs-lookup"><span data-stu-id="d6061-166">An operation specialization consists of the specialization tag (like e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="d6061-167">En explicit deklaration enligt beskrivningen nedan.</span><span class="sxs-lookup"><span data-stu-id="d6061-167">An explicit declaration as described below.</span></span>
- <span data-ttu-id="d6061-168">Ett direktiv som talar om för kompileraren hur du genererar specialiseringen, en av:</span><span class="sxs-lookup"><span data-stu-id="d6061-168">A directive that tells the compiler how to generate the specialization, one of:</span></span>
  - <span data-ttu-id="d6061-169">`intrinsic`, som anger att specialiseringen tillhandahålls av mål datorn.</span><span class="sxs-lookup"><span data-stu-id="d6061-169">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="d6061-170">`distribute`som kan användas med `controlled` och `controlled adjoint` specialiseringar.</span><span class="sxs-lookup"><span data-stu-id="d6061-170">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="d6061-171">När det används med `controlled`anger det att kompilatorn ska beräkna specialiseringen genom att tillämpa `Controlled` på alla åtgärder i `body`.</span><span class="sxs-lookup"><span data-stu-id="d6061-171">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="d6061-172">När det används med `controlled adjoint`anger det att kompilatorn ska beräkna specialiseringen genom att tillämpa `Controlled` på alla åtgärder i `adjoint` specialisering.</span><span class="sxs-lookup"><span data-stu-id="d6061-172">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="d6061-173">`invert`, som anger att kompilatorn ska beräkna `adjoint` specialisering genom att invertera `body`, dvs. ändra ordningen på åtgärderna och tillämpa den angränsande i var och en.</span><span class="sxs-lookup"><span data-stu-id="d6061-173">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="d6061-174">När det används med `adjoint controlled`anger detta att kompilatorn ska beräkna specialiseringen genom att invertera `controlled` specialisering.</span><span class="sxs-lookup"><span data-stu-id="d6061-174">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="d6061-175">`self`för att indikera att den angränsande specialiseringen är samma som den `body` specialiseringen.</span><span class="sxs-lookup"><span data-stu-id="d6061-175">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="d6061-176">Detta är giltigt för `adjoint` och `adjoint controlled` specialiseringar.</span><span class="sxs-lookup"><span data-stu-id="d6061-176">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="d6061-177">För `adjoint controlled`innebär `self` att `adjoint controlled` specialisering är samma som `controlled` specialisering.</span><span class="sxs-lookup"><span data-stu-id="d6061-177">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="d6061-178">`auto`för att ange att kompilatorn ska välja ett lämpligt direktiv att tillämpa.</span><span class="sxs-lookup"><span data-stu-id="d6061-178">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="d6061-179">`auto` får inte användas för `body` specialisering.</span><span class="sxs-lookup"><span data-stu-id="d6061-179">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="d6061-180">Direktiven och `auto` alla kräver ett avslutande semikolon `;`.</span><span class="sxs-lookup"><span data-stu-id="d6061-180">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="d6061-181">`auto`-direktivet matchar följande generations direktiv om en explicit deklaration av `body` tillhandahålls:</span><span class="sxs-lookup"><span data-stu-id="d6061-181">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="d6061-182">`adjoint` specialisering skapas enligt direktivet `invert`.</span><span class="sxs-lookup"><span data-stu-id="d6061-182">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="d6061-183">`controlled` specialisering skapas enligt direktivet `distribute`.</span><span class="sxs-lookup"><span data-stu-id="d6061-183">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="d6061-184">`adjoint controlled` specialisering skapas enligt direktivet `invert` om en explicit deklaration för `controlled` anges, men inte en för `adjoint`, och `distribute` annars.</span><span class="sxs-lookup"><span data-stu-id="d6061-184">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="d6061-185">Om en åtgärd är självständig kan du uttryckligen ange antingen den angränsande eller den kontrollerade inangränsandea specialiseringen via generationens direktiv `self` för att tillåta att kompileraren använder den informationen i optimerings syfte.</span><span class="sxs-lookup"><span data-stu-id="d6061-185">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="d6061-186">En specialiserings deklaration som innehåller en användardefinierad implementering består av en argument tupel följt av ett instruktions block med den Q #-kod som implementerar specialiseringen.</span><span class="sxs-lookup"><span data-stu-id="d6061-186">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="d6061-187">I argument listan används `...` för att representera argumenten som har deklarerats för åtgärden som helhet.</span><span class="sxs-lookup"><span data-stu-id="d6061-187">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="d6061-188">För `body` och `adjoint`bör argument listan alltid vara `(...)`; för `controlled` och `adjoint controlled`ska argument listan vara en symbol som representerar matrisen med kontroll qubits, följt av `...`, inom parentes; till exempel `(controls,...)`.</span><span class="sxs-lookup"><span data-stu-id="d6061-188">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

<span data-ttu-id="d6061-189">Om en eller flera specialiseringar förutom standard texten måste deklareras explicit måste implementeringen för standard texten omslutas till en lämplig specialiserings deklaration.</span><span class="sxs-lookup"><span data-stu-id="d6061-189">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a><span data-ttu-id="d6061-190">Angränsande</span><span class="sxs-lookup"><span data-stu-id="d6061-190">Adjoint</span></span>

<span data-ttu-id="d6061-191">Den angränsande av en åtgärd anger hur den komplexa konjugatet för åtgärden implementeras, d.v.s. hur åtgärden fungerar när "körs i omvänd ordning".</span><span class="sxs-lookup"><span data-stu-id="d6061-191">The adjoint of an operation specifies how the complex conjugate transpose of the operation is implemented, i.e. how the operation acts when "run in reverse".</span></span>
<span data-ttu-id="d6061-192">Det är tillåtet att ange en åtgärd utan angränsande; mätnings åtgärder har till exempel inget angränsande eftersom de inte är inverteras.</span><span class="sxs-lookup"><span data-stu-id="d6061-192">It is legal to specify an operation with no adjoint; for instance, measurement operations have no adjoint because they are not invertible.</span></span>
<span data-ttu-id="d6061-193">En åtgärd stöder `Adjoint` Functor om dess deklaration innehåller en implicit eller explicit deklaration av en närliggande specialisering.</span><span class="sxs-lookup"><span data-stu-id="d6061-193">An operation supports the `Adjoint` functor if its declaration contains an implicit or explicit declaration of an adjoint specialization.</span></span>
<span data-ttu-id="d6061-194">En explicit deklarerad, intilliggande, intilliggande specialisering innebär att det finns en närliggande specialisering.</span><span class="sxs-lookup"><span data-stu-id="d6061-194">An explicitly declared controlled adjoint specialization implies the existence of an adjoint specialization.</span></span> 

<span data-ttu-id="d6061-195">För åtgärder vars brödtext innehåller upprepnings-tills-Success-slingor, set-instruktioner, mätningar, Return-instruktioner eller anrop till andra åtgärder som inte har stöd för `Adjoint` Functor, genererar automatiskt en angränsande specialisering enligt `invert`-eller `auto`-direktivet.</span><span class="sxs-lookup"><span data-stu-id="d6061-195">For operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

### <a name="controlled"></a><span data-ttu-id="d6061-196">Styr</span><span class="sxs-lookup"><span data-stu-id="d6061-196">Controlled</span></span>

<span data-ttu-id="d6061-197">Den kontrollerade versionen av en åtgärd anger hur en Quantum-kontrollerad version av åtgärden implementeras, t. ex. hur en åtgärd fungerar när den tillämpas på tillståndet för ett Quantum-register.</span><span class="sxs-lookup"><span data-stu-id="d6061-197">The controlled version of an operation specifies how a quantum-controlled version of the operation is implemented, i.e. how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="d6061-198">En fullständig beskrivning finns i det [styrda](xref:microsoft.quantum.language.type-model#controlled) avsnittet.</span><span class="sxs-lookup"><span data-stu-id="d6061-198">A more complete description is provided in the [Controlled](xref:microsoft.quantum.language.type-model#controlled) section.</span></span>

<span data-ttu-id="d6061-199">Det är tillåtet att ange en åtgärd utan styrd version. till exempel har mått åtgärderna ingen styrd version eftersom de inte är styrda.</span><span class="sxs-lookup"><span data-stu-id="d6061-199">It is legal to specify an operation with no controlled version; for instance, measurement operations have no controlled version because they are not controllable.</span></span>
<span data-ttu-id="d6061-200">En åtgärd stöder `Controlled`-Functor om och endast om dess deklaration innehåller en implicit eller explicit deklaration av en kontrollerad specialisering.</span><span class="sxs-lookup"><span data-stu-id="d6061-200">An operation supports the `Controlled` functor if and only if its declaration contains an implicit or explicit declaration of a controlled specialization.</span></span>
<span data-ttu-id="d6061-201">En explicit deklarerad, intilliggande, intilliggande specialisering innebär att en kontrollerad specialisering förekommer.</span><span class="sxs-lookup"><span data-stu-id="d6061-201">An explicitly declared controlled adjoint specialization implies the existence of a controlled specialization.</span></span> 

<span data-ttu-id="d6061-202">För en åtgärd vars brödtext innehåller anrop till andra åtgärder som inte stöder `Controlled` Functor, genererar automatiskt en kontrollerad specialisering som följer `distribute` eller `auto` direktivet.</span><span class="sxs-lookup"><span data-stu-id="d6061-202">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

### <a name="controlled-adjoint"></a><span data-ttu-id="d6061-203">Kontrollerat från det intilliggande</span><span class="sxs-lookup"><span data-stu-id="d6061-203">Controlled Adjoint</span></span>

<span data-ttu-id="d6061-204">Den kontrollerade, intilliggande versionen av en åtgärd anger hur en Quantum-kontrollerad version av åtgärdens angränsande funktion implementeras.</span><span class="sxs-lookup"><span data-stu-id="d6061-204">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="d6061-205">Det är tillåtet att ange en åtgärd utan kontrollerad version. till exempel har mått åtgärderna ingen kontrollerad, angränsande version eftersom de varken kan styras eller inverteras.</span><span class="sxs-lookup"><span data-stu-id="d6061-205">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="d6061-206">En kontrollerad, angränsande specialisering för en åtgärd måste finnas om och endast om både en intilliggande och en kontrollerad specialisering finns.</span><span class="sxs-lookup"><span data-stu-id="d6061-206">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="d6061-207">I så fall härleds förekomsten av den kontrollerade angränsande specialiseringen och en lämplig specialisering genereras av kompilatorn om ingen implementering har definierats explicit.</span><span class="sxs-lookup"><span data-stu-id="d6061-207">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="d6061-208">För en åtgärd vars brödtext innehåller anrop till andra åtgärder som inte har en kontrollerad version som inte är en kontrollerad version, genererar automatiskt en angränsande specialisering efter `invert`, `distribute` eller `auto`-direktivet inte är möjligt.</span><span class="sxs-lookup"><span data-stu-id="d6061-208">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="examples"></a><span data-ttu-id="d6061-209">Exempel</span><span class="sxs-lookup"><span data-stu-id="d6061-209">Examples</span></span>

<span data-ttu-id="d6061-210">En åtgärds deklaration kan vara så enkel som följande, som definierar den primitiva Pauli X-åtgärden:</span><span class="sxs-lookup"><span data-stu-id="d6061-210">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

<span data-ttu-id="d6061-211">Följande definierar Teleport-åtgärden.</span><span class="sxs-lookup"><span data-stu-id="d6061-211">The following defines the teleport operation.</span></span>

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation PrepareEntangledPair (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        PrepareEntangledPair(target, ancilla);

        // Do the teleportation
        Adjoint PrepareEntangledPair(ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a><span data-ttu-id="d6061-212">Funktions deklarationer</span><span class="sxs-lookup"><span data-stu-id="d6061-212">Function Declarations</span></span>

<span data-ttu-id="d6061-213">Functions är rent klassiska rutiner i Q #.</span><span class="sxs-lookup"><span data-stu-id="d6061-213">Functions are purely classical routines in Q#.</span></span>
<span data-ttu-id="d6061-214">Varje Q #-källfil kan definiera valfritt antal funktioner.</span><span class="sxs-lookup"><span data-stu-id="d6061-214">Each Q# source file may define any number of functions.</span></span>

<span data-ttu-id="d6061-215">En funktions deklaration består av nyckelordet `function`följt av symbolen som är funktionens namn, en typ av identifierare, en typ anteckning som beskriver funktionens returtyp och ett instruktions block som beskriver implementeringen av funktionen.</span><span class="sxs-lookup"><span data-stu-id="d6061-215">A function declaration consists of the keyword `function`, followed by the symbol that is the function’s name, a typed identifier tuple, a type annotation that describes the function's return type, and a statement block that describes the implementation of the function.</span></span>

<span data-ttu-id="d6061-216">Instruktions blocket som definierar en funktion måste stå inom `{` och `}` som alla andra instruktions block.</span><span class="sxs-lookup"><span data-stu-id="d6061-216">The statement block defining a function must be enclosed in `{` and `}` like any other statement block.</span></span>

<span data-ttu-id="d6061-217">Funktions namn måste vara unika inom ett namn område och kan inte vara i konflikt med åtgärds-och typnamn.</span><span class="sxs-lookup"><span data-stu-id="d6061-217">Function names must be unique within a namespace and may not conflict with operation and type names.</span></span>
<span data-ttu-id="d6061-218">Funktioner får inte allokera eller låna qubits eller anropa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="d6061-218">Functions may not allocate or borrow qubits, or call operations.</span></span> <span data-ttu-id="d6061-219">En partiell tillämpning av åtgärder eller överföring av värden i åtgärds typ är bra.</span><span class="sxs-lookup"><span data-stu-id="d6061-219">Partial application of operations or passing around operation typed values is fine.</span></span>

<span data-ttu-id="d6061-220">Exempel:</span><span class="sxs-lookup"><span data-stu-id="d6061-220">For example,</span></span>

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```


## <a name="internal-declarations"></a><span data-ttu-id="d6061-221">Interna deklarationer</span><span class="sxs-lookup"><span data-stu-id="d6061-221">Internal Declarations</span></span>

<span data-ttu-id="d6061-222">Användardefinierade typer, åtgärder och funktioner kan också deklareras som *interna*.</span><span class="sxs-lookup"><span data-stu-id="d6061-222">User-defined types, operations, and functions can also be declared as *internal*.</span></span>
<span data-ttu-id="d6061-223">Det innebär att de endast kan nås från det Q #-projekt som de är deklarerade i.</span><span class="sxs-lookup"><span data-stu-id="d6061-223">This means that they can only be accessed from within the Q# project that they are declared in.</span></span>
<span data-ttu-id="d6061-224">När ett projekt används som referens görs alla *offentliga* (icke-interna) deklarationer tillgängliga, men om du försöker använda en intern deklaration från ett annat projekt skapas ett fel.</span><span class="sxs-lookup"><span data-stu-id="d6061-224">When a project is used as a reference, all of its *public* (non-internal) declarations are made available, but trying to use an internal declaration from another project will produce an error.</span></span>
<span data-ttu-id="d6061-225">Interna deklarationer är användbara för att skriva modulär kod som kan återanvändas av andra delar av projektet, men fortfarande ändras senare utan att du behöver bryta andra projekt som kan vara beroende av den.</span><span class="sxs-lookup"><span data-stu-id="d6061-225">Internal declarations are useful for writing modular code that can be reused by other parts of your project, but still be changed later without breaking other projects that might depend on it.</span></span>

<span data-ttu-id="d6061-226">En intern användardefinierad typ, åtgärd eller funktion kan deklareras genom att du lägger till `internal` i början av deklarationen.</span><span class="sxs-lookup"><span data-stu-id="d6061-226">An internal user-defined type, operation, or function can be declared simply by adding `internal` at the beginning of the declaration.</span></span>
<span data-ttu-id="d6061-227">Exempel:</span><span class="sxs-lookup"><span data-stu-id="d6061-227">For example,</span></span>

```qsharp
internal newtype PairOfQubits = (Qubit, Qubit);

internal operation PrepareEntangledPair(pair : PairOfQubits) : Unit 
is Adj + Ctl {
    let (q1, q2) = pair!;
    H(q2);
    CNOT(q2, q1);
}

internal function DotProduct(a : Double[], b : Double[]) : Double {
    ...
}
```

> [!WARNING]
> <span data-ttu-id="d6061-228">Interna användardefinierade typer kan bara användas i signaturer eller underliggande typer om motsvarande anropande eller användardefinierade typ också är intern.</span><span class="sxs-lookup"><span data-stu-id="d6061-228">Internal user-defined types can only be used in signatures or underlying types if the corresponding callable or user-defined type is also internal.</span></span>
> <span data-ttu-id="d6061-229">Om det till exempel finns en användardefinierad typ `InternalOptions` som deklarerades med nyckelordet `internal`, kommer följande deklarationer leda till fel:</span><span class="sxs-lookup"><span data-stu-id="d6061-229">For example, if there is a user-defined type `InternalOptions` that was declared with the `internal` keyword, then the following declarations will result in errors:</span></span>
>
> ```qsharp
> // Error: Can't use InternalOptions as an output type of a public function.
> function DefaultInternalOptions() : InternalOptions { ... }
>
> // Error: Can't use InternalOptions as an item in a public user-defined type.
> newtype ExtendedOptions = (Internal : InternalOptions);
> ```
