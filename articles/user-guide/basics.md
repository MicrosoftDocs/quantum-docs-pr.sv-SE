---
title: 'Q #-grunder'
description: 'Grundläggande begrepp för Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: fd0ea47f00b1456ec460808ef7d451c8427677cd
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431163"
---
# <a name="q-basics"></a><span data-ttu-id="eb77c-103">Q #-grunder</span><span class="sxs-lookup"><span data-stu-id="eb77c-103">Q# Basics</span></span>

<span data-ttu-id="eb77c-104">I det här avsnittet presenterar vi en kort introduktion till de grundläggande Bygg stenarna för Q #.</span><span class="sxs-lookup"><span data-stu-id="eb77c-104">In this section we present a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="eb77c-105">En snabb översikt över vad Q # är och var det passar in som en grundläggande komponent i Quantum Development Kit, kan du titta på [Vad är Q #?](xref:microsoft.quantum.overview.q-sharp).</span><span class="sxs-lookup"><span data-stu-id="eb77c-105">For a quick overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, you can check out [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="eb77c-106">Vad är ett Quantum-program?</span><span class="sxs-lookup"><span data-stu-id="eb77c-106">What is a quantum program?</span></span>

<span data-ttu-id="eb77c-107">Från ett tekniskt perspektiv kan ett Quantum-program ses som en viss uppsättning klassiska under rutiner som, vid anrop, utför vissa åtgärder på ett Quantum-system.</span><span class="sxs-lookup"><span data-stu-id="eb77c-107">From a technical perspective, a quantum program can be seen as a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="eb77c-108">En viktig följd av den vyn är att ett program som skrivits i Q # inte direkt modellerar qubits själva, utan beskriver i stället hur en klassisk kontroll dator interagerar med dessa qubits.</span><span class="sxs-lookup"><span data-stu-id="eb77c-108">An important consequence of that view is that a program written in Q# does not directly model qubits themselves, but rather describes how a classical control computer interacts with those qubits.</span></span>
<span data-ttu-id="eb77c-109">Enligt design definierar Q # alltså inte Quantum-tillstånd eller andra egenskaper för Quantum Mechanics direkt.</span><span class="sxs-lookup"><span data-stu-id="eb77c-109">By design, Q# thus does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="eb77c-110">Anta till exempel att State $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ beskrivs i guiden för [Quantum Computing-koncept](xref:microsoft.quantum.concepts.intro) .</span><span class="sxs-lookup"><span data-stu-id="eb77c-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="eb77c-111">För att förbereda det här läget i Q #, använder vi de fakta som qubits initieras i $ \ket {0} $ State och att $ \ket{+} = H\ket {0} $, där $H $ är Hadamard-transformeringen, som implementeras av [ `H` åtgärd] (] (XREF: Microsoft. Quantum. inre. H):</span><span class="sxs-lookup"><span data-stu-id="eb77c-111">To prepare this state in Q#, we use the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the Hadamard transform, implemented by the [`H` operation](](xref:microsoft.quantum.intrinsic.h):</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a><span data-ttu-id="eb77c-112">Quantum-tillstånd i Q #</span><span class="sxs-lookup"><span data-stu-id="eb77c-112">Quantum states in Q#</span></span>

<span data-ttu-id="eb77c-113">Det är viktigt att i Skriv programmet ovan inte uttryckligen referera till statusen inom Q #, utan att i stället se hur tillstånd har *omvandlats* av vårt program.</span><span class="sxs-lookup"><span data-stu-id="eb77c-113">Importantly, in writing the above program, we did not explicitly refer to the state within Q#, but rather described how the state was *transformed* by our program.</span></span>
<span data-ttu-id="eb77c-114">På så sätt kan vi helt oberoende om vad ett Quantum-tillstånd *är* även på varje måldator, vilket kan ha olika tolkningar beroende på datorn.</span><span class="sxs-lookup"><span data-stu-id="eb77c-114">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="eb77c-115">Ett Q #-program kan inte Introspect till en qubit.</span><span class="sxs-lookup"><span data-stu-id="eb77c-115">A Q# program has no ability to introspect into the state of a qubit.</span></span>
<span data-ttu-id="eb77c-116">Ett program kan istället anropa åtgärder, till exempel [`Measure`](xref:microsoft.quantum.intrinsic.measure) för att lära sig information från en qubit och anropa åtgärder som [`X`](xref:microsoft.quantum.intrinsic.x) och [`H`](xref:microsoft.quantum.intrinsic.h) för att agera för en qubit.</span><span class="sxs-lookup"><span data-stu-id="eb77c-116">Rather, a program can call operations such as [`Measure`](xref:microsoft.quantum.intrinsic.measure) to learn information from a qubit, and call operations such as [`X`](xref:microsoft.quantum.intrinsic.x) and [`H`](xref:microsoft.quantum.intrinsic.h) to act on the state of a qubit.</span></span>
<span data-ttu-id="eb77c-117">De här *åtgärderna faktiskt görs* enbart konkret av mål datorn som vi använder för att köra ett visst Q #-program.</span><span class="sxs-lookup"><span data-stu-id="eb77c-117">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>
<span data-ttu-id="eb77c-118">Om du till exempel kör programmet i hela den här [simulatorn](xref:microsoft.quantum.machines.full-state-simulator)utför simulatorn motsvarande matematiska åtgärder till det simulerade Quantum-systemet.</span><span class="sxs-lookup"><span data-stu-id="eb77c-118">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator will perform the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="eb77c-119">Men om mål datorn är en verklig Quantum-dator och du tittar på framtiden, så dirigerar de här åtgärderna i Q # den Quantum datorn för att utföra motsvarande *verkliga* åtgärder på det *verkliga* Quantum-systemet (t. ex. exakta tids bara laser pulser).</span><span class="sxs-lookup"><span data-stu-id="eb77c-119">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="eb77c-120">Ett Q #-program kombinerar dessa åtgärder så som definieras av en mål dator för att skapa nya, högre åtgärder för att uttrycka Quantum-beräkning.</span><span class="sxs-lookup"><span data-stu-id="eb77c-120">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="eb77c-121">På så sätt gör Q # det enkelt att uttrycka logiken för de underliggande Quantum-och hybrid Quantum-algoritmerna, samtidigt som det är allmänt vad gäller strukturen för en mål dator eller Simulator.</span><span class="sxs-lookup"><span data-stu-id="eb77c-121">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="q-operations-and-functions"></a><span data-ttu-id="eb77c-122">Q #-åtgärder och-funktioner</span><span class="sxs-lookup"><span data-stu-id="eb77c-122">Q# operations and functions</span></span>

<span data-ttu-id="eb77c-123">Konkret är ett Q #-program bestående av *åtgärder*, *funktioner*och andra användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="eb77c-123">Concretely, a Q# program is comprised of *operations*, *functions*, and any user-defined types.</span></span> 

<span data-ttu-id="eb77c-124">Åtgärder används för att beskriva omvandlingar av Quantum Systems och är de mest grundläggande Bygg stenarna för Q #-program.</span><span class="sxs-lookup"><span data-stu-id="eb77c-124">Operations are used to describe the transformations of quantum systems and are the most basic building block of Q# programs.</span></span> <span data-ttu-id="eb77c-125">Varje åtgärd som definierats i Q # kan sedan anropa valfritt antal andra åtgärder.</span><span class="sxs-lookup"><span data-stu-id="eb77c-125">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="eb77c-126">Till skillnad från åtgärder används funktioner för att beskriva rent *deterministiskt* klassiskt klassiskt beteende och har inga effekter, förutom att beräkna klassiska värden.</span><span class="sxs-lookup"><span data-stu-id="eb77c-126">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="eb77c-127">Anta till exempel att vi vill mäta våra qubits i slutet av ett program och lägga till mått resultatet i en matris.</span><span class="sxs-lookup"><span data-stu-id="eb77c-127">For example, suppose we would like to measure our qubits at the end of a program, and add the measurement results to an array.</span></span>
<span data-ttu-id="eb77c-128">I det här fallet `Measure` är en *åtgärd* som instruerar mål datorn att utföra en mätning på (verklig eller simulerad) qubits, och den klassiska processen för att lägga till de returnerade resultaten i en matris hanteras av *Functions*.</span><span class="sxs-lookup"><span data-stu-id="eb77c-128">In this case `Measure` is an *operation* which instructs the target machine to perform a measurement on the (real or simulated) qubits, and the classical process of adding the returned results to an array will be handled by *functions*.</span></span>

<span data-ttu-id="eb77c-129">Åtgärder och funktioner kallas för *callables*, och deras underliggande struktur och beteende införs på sidan [åtgärder och funktioner på Q #](xref:microsoft.quantum.guide.operationsfunctions) .</span><span class="sxs-lookup"><span data-stu-id="eb77c-129">Together, operations and functions are referred to as *callables*, and their underlying structure and behavior is introduced on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) page.</span></span>


## <a name="q-syntax-overview"></a><span data-ttu-id="eb77c-130">Översikt över Q # syntax</span><span class="sxs-lookup"><span data-stu-id="eb77c-130">Q# syntax overview</span></span>

<span data-ttu-id="eb77c-131">Syntaxen för ett språk beskriver de olika kombinationer av symboler som utgör ett syntaktiskt korrekt program.</span><span class="sxs-lookup"><span data-stu-id="eb77c-131">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="eb77c-132">I Q # kan vi klassificera elementen i dess syntax i tre olika grupper: typer, uttryck och uttryck.</span><span class="sxs-lookup"><span data-stu-id="eb77c-132">In Q# we can classify the elements of its syntax in three different groups: types, expressions and statements.</span></span>

### <a name="types"></a><span data-ttu-id="eb77c-133">Typer</span><span class="sxs-lookup"><span data-stu-id="eb77c-133">Types</span></span>
<span data-ttu-id="eb77c-134">Q # är ett starkt skrivet språk, så att en noggrann användning av typer kan hjälpa kompilatorn att tillhandahålla starka garantier för Q #-program vid kompilering.</span><span class="sxs-lookup"><span data-stu-id="eb77c-134">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="eb77c-135">Förutom standard-och Quantum-/regionsspecifika inbyggda primitiva typer (t. ex.,, `Int` `Bool` `Qubit` och `Result` ) ger Q # stöd för användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="eb77c-135">In addition to standard and quantum-specific built-in primitive types (e.g. `Int`, `Bool`, `Qubit`, and `Result`), Q# provides support for user-defined types.</span></span>
<span data-ttu-id="eb77c-136">Alla typer av olika typer av Q # beskrivs på sidan [typer i Q #](xref:microsoft.quantum.guide.types) , tillsammans med information om matris-och tuple-typer, samt hur du definierar nya typer i en Q #-fil.</span><span class="sxs-lookup"><span data-stu-id="eb77c-136">All of Q#'s various primitive types are described on the [Types in Q#](xref:microsoft.quantum.guide.types) page, along with details on array and tuple types, as well as how to define new types within a Q# file.</span></span>

### <a name="expressions"></a><span data-ttu-id="eb77c-137">Uttryck</span><span class="sxs-lookup"><span data-stu-id="eb77c-137">Expressions</span></span>
<span data-ttu-id="eb77c-138">Ett uttryck i ett programmeringsspråk är en kombination av en eller flera konstanter, variabler, operatorer och funktioner som programmerings språket tolkar och utvärderar till ett särskilt värde.</span><span class="sxs-lookup"><span data-stu-id="eb77c-138">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="eb77c-139">För varje typ på ett språk kan exempelvis uttryck av den typen vara antingen *litteraler* eller symboler som är kopplade till ett värde av den typen.</span><span class="sxs-lookup"><span data-stu-id="eb77c-139">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="eb77c-140">Till exempel `5` är en `Int` literal (vilket även ett uttryck av typen `Int` ) och om symbolen `count` är kopplad till heltal svärdet `5` är det `count` också ett heltals uttryck.</span><span class="sxs-lookup"><span data-stu-id="eb77c-140">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="eb77c-141">Dessutom kan ett uttryck bestå av andra uttryck tillsammans med vissa operatorer.</span><span class="sxs-lookup"><span data-stu-id="eb77c-141">Additionally, an expression can consist of other expressions combined with certain operators.</span></span>
<span data-ttu-id="eb77c-142">Ett annat exempel på ett `Int` uttryck som utvärderas till `5` är `2+3` .</span><span class="sxs-lookup"><span data-stu-id="eb77c-142">Hence another example of an `Int` expression which evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="eb77c-143">De möjliga uttrycken av typer i Q #, samt de kompatibla operatorer som kan användas för att forma dem, beskrivs i [typ uttrycken på Q #](xref:microsoft.quantum.guide.expressions) -sidan.</span><span class="sxs-lookup"><span data-stu-id="eb77c-143">The possible expressions of types in Q#, as well as the compatible operators that can be used to form them, are detailed on the [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) page.</span></span> 

### <a name="statements"></a><span data-ttu-id="eb77c-144">Instruktioner</span><span class="sxs-lookup"><span data-stu-id="eb77c-144">Statements</span></span> 
<span data-ttu-id="eb77c-145">En instruktion är en syntaktisk enhet av ett tvingande programmeringsspråk som uttrycker åtgärder som ska utföras. Uttryck med uttryck i dessa instruktioner returnerar inte resultat och utförs enbart för sina sido effekter, medan uttryck alltid returnerar ett resultat och ofta inte har sido effekter alls.</span><span class="sxs-lookup"><span data-stu-id="eb77c-145">A statement is a syntactic unit of an imperative programming language that expresses some action to be carried out. Statements contrast with expressions in that statements do not return results and are executed solely for their side effects, while expressions always return a result and often do not have side effects at all.</span></span>
<span data-ttu-id="eb77c-146">Denna åtskillnad observeras ofta i formuleringen: ett uttryck utvärderas, medan en instruktion körs.</span><span class="sxs-lookup"><span data-stu-id="eb77c-146">This distinction is frequently observed in wording: an expression is evaluated, whereas a statement is executed.</span></span>

<span data-ttu-id="eb77c-147">Ett mycket grundläggande exempel på en instruktion i Q # tilldelar en symbol till ett uttryck:</span><span class="sxs-lookup"><span data-stu-id="eb77c-147">A very basic example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="eb77c-148">Ett något mer intressant exempel är den `for` instruktion som stöder iteration och innehåller ett *instruktions block*.</span><span class="sxs-lookup"><span data-stu-id="eb77c-148">A slightly more interesting example is the `for` statement which supports iteration and includes a *statement block*.</span></span>
<span data-ttu-id="eb77c-149">Anta `qubits` att är symbolen knuten till ett register över qubits (tekniskt av typen `Qubit[]` , dvs. en matris av `Qubit` typer).</span><span class="sxs-lookup"><span data-stu-id="eb77c-149">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, i.e. an array of `Qubit` types).</span></span> <span data-ttu-id="eb77c-150">Dra</span><span class="sxs-lookup"><span data-stu-id="eb77c-150">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="eb77c-151">är en instruktion som itererar över varje qubit i registret, vilket utför `H` åtgärden på var och en.</span><span class="sxs-lookup"><span data-stu-id="eb77c-151">is a statement which iterates over each qubit in the register, performing the `H` operation on each.</span></span> <span data-ttu-id="eb77c-152">Observera att `H(qubit);` även är en instruktion i sig själv.</span><span class="sxs-lookup"><span data-stu-id="eb77c-152">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="eb77c-153">I själva verket kan alla anrops uttryck av typen `Unit` (de callables som inte returnerar information) användas som en instruktion.</span><span class="sxs-lookup"><span data-stu-id="eb77c-153">In fact, any call expression of type `Unit` (those callables that do not return any information) may be used as a statement.</span></span>
<span data-ttu-id="eb77c-154">Detta används främst när du anropar åtgärder på qubits som returneras `Unit` eftersom syftet med instruktionen är att ändra implicit Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="eb77c-154">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="eb77c-155">Uttrycks utvärderings uttryck kräver ett avslutande semikolon.</span><span class="sxs-lookup"><span data-stu-id="eb77c-155">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="eb77c-156">Nästan alla aspekter av ett Q #-program skapas med hjälp av instruktioner, så att ingen enskild sida kan omfatta all information som rör dem.</span><span class="sxs-lookup"><span data-stu-id="eb77c-156">Nearly every aspect of a Q# program is built using statements, so no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="eb77c-157">Deras lexikala struktur och formatering beskrivs i avsnittet om [fil struktur för Q #](xref:microsoft.quantum.guide.filestructure) , symbol bindnings tilldelning och omfattning vid [variabler i q #](xref:microsoft.quantum.guide.variables)och kontroll av flödes slingor, till exempel `for` vid [kontroll flöde i q #](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="eb77c-157">However, their lexical structure and formatting is described on the [Q# File Structure](xref:microsoft.quantum.guide.filestructure) page, symbol binding assignment and scope at [Variables in Q#](xref:microsoft.quantum.guide.variables), and control flow loops such as `for` at [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>


## <a name="whats-next"></a><span data-ttu-id="eb77c-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="eb77c-158">What's next?</span></span>
<span data-ttu-id="eb77c-159">I resten av den här guiden visar vi hur du använder Q # för att skapa komplexa Quantum-program genom de grundläggande Bygg stenarna för åtgärder, funktioner och typer.</span><span class="sxs-lookup"><span data-stu-id="eb77c-159">Throughout the rest of this guide, we will show you how to use Q# to construct complex quantum programs through the basic building blocks of operations, functions, and types.</span></span>

<span data-ttu-id="eb77c-160">Du kan börja lära dig om [typer i Q #](xref:microsoft.quantum.guide.types)för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="eb77c-160">To get started, you can start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="eb77c-161">Om du är intresse rad av att lära dig mer om grunderna och motivation bakom Q #, kolla [Varför behöver vi Q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span><span class="sxs-lookup"><span data-stu-id="eb77c-161">If you are interested in learning more about the foundations and motivation behind Q#, check out [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
