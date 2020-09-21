---
title: Åtgärder och funktioner i Q#
description: Så här definierar och anropar du åtgärder och funktioner, och de kontrollerade och angränsande drifts specialiseringarna.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- Q#
- $$v
ms.openlocfilehash: c2ce999ea2a0fe7204f402fedb4cd3a3c15bd44b
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759432"
---
# <a name="operations-and-functions-in-no-locq"></a><span data-ttu-id="af111-103">Åtgärder och funktioner i Q#</span><span class="sxs-lookup"><span data-stu-id="af111-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="af111-104">Definiera nya åtgärder</span><span class="sxs-lookup"><span data-stu-id="af111-104">Defining New Operations</span></span>

<span data-ttu-id="af111-105">Åtgärder är kärnan i Q# .</span><span class="sxs-lookup"><span data-stu-id="af111-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="af111-106">När de har deklarerats kan de antingen anropas från klassiska .NET-program, till exempel med hjälp av en simulator eller av andra åtgärder i Q# .</span><span class="sxs-lookup"><span data-stu-id="af111-106">Once declared, they can either be called from classical .NET applications, for example, using a simulator or by other operations within Q#.</span></span>
<span data-ttu-id="af111-107">Varje åtgärd som definierats i Q# kan anropa valfritt antal andra åtgärder, inklusive de inbyggda inbyggda operationerna som definieras av språket.</span><span class="sxs-lookup"><span data-stu-id="af111-107">Each operation defined in Q# can call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="af111-108">Det specifika sätt som Q# definierar dessa inre åtgärder beror på mål datorn.</span><span class="sxs-lookup"><span data-stu-id="af111-108">The particular way in which Q# defines these intrinsic operations depends on the target machine.</span></span>
<span data-ttu-id="af111-109">När de kompileras visas varje åtgärd som en .NET-klass typ som kan tillhandahållas mål datorer.</span><span class="sxs-lookup"><span data-stu-id="af111-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="af111-110">Varje Q# källfil kan definiera ett valfritt antal åtgärder.</span><span class="sxs-lookup"><span data-stu-id="af111-110">Each Q# source file can define any number of operations.</span></span>
<span data-ttu-id="af111-111">Åtgärds namn måste vara unika inom ett namn område och kan inte stå i konflikt med typ-eller funktions namn.</span><span class="sxs-lookup"><span data-stu-id="af111-111">Operation names must be unique within a namespace and can not conflict with type or function names.</span></span>

<span data-ttu-id="af111-112">En åtgärds deklaration består av nyckelordet `operation` , följt av symbolen som är åtgärdens namn, en typ av identifierare som definierar argumenten för åtgärden, ett kolon `:` , en typ anteckning som beskriver åtgärdens resultat typ, eventuellt en anteckning med åtgärds egenskaper, en öppen klammerparentes och sedan texten i åtgärds deklarationen som omges av klammerparenteser `{ }` .</span><span class="sxs-lookup"><span data-stu-id="af111-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace, and then the body of the operation declaration, enclosed in braces `{ }`.</span></span>

<span data-ttu-id="af111-113">Varje åtgärd tar indata, genererar utdata och anger implementeringen för en eller flera åtgärds specialiseringar.</span><span class="sxs-lookup"><span data-stu-id="af111-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="af111-114">De möjliga specialiseringarna och hur du definierar och anropar dem beskrivs i de olika avsnitten i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="af111-114">The possible specializations, and how to define and call them, are detailed in the different sections of this article.</span></span>
<span data-ttu-id="af111-115">I den här övningen ska du ta hänsyn till följande åtgärd, som endast definierar en fördefinierad specialisering och använder en enda qubit som inmatad, och anropar sedan den inbyggda <xref:microsoft.quantum.intrinsic.x> åtgärden för inaktuella ingången:</span><span class="sxs-lookup"><span data-stu-id="af111-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="af111-116">Nyckelordet `operation` inleder åtgärds definitionen, följt av namnet. här, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="af111-116">The keyword `operation` begins the operation definition, followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="af111-117">Därefter definieras indatatypen ( `Qubit` ), tillsammans med ett namn, `target` för att referera till indatamängden i den nya åtgärden.</span><span class="sxs-lookup"><span data-stu-id="af111-117">Next, the type of input is defined (`Qubit`), along with a name, `target`, for referring to the input within the new operation.</span></span>
<span data-ttu-id="af111-118">Till sist `Unit` definierar den här åtgärdens utdata tom.</span><span class="sxs-lookup"><span data-stu-id="af111-118">Lastly, `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="af111-119">`Unit` används på samma sätt som `void` i C# och andra tvingande språk och motsvarar `unit` i F # och andra funktionella språk.</span><span class="sxs-lookup"><span data-stu-id="af111-119">`Unit` is used similarly to `void` in C# and other imperative languages and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="af111-120">Åtgärder kan också returnera fler intressanta typer än `Unit` .</span><span class="sxs-lookup"><span data-stu-id="af111-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="af111-121">Till exempel <xref:microsoft.quantum.intrinsic.m> returnerar åtgärden utdata av typen `Result` , vilket representerar att ha utfört ett mått.</span><span class="sxs-lookup"><span data-stu-id="af111-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span>  <span data-ttu-id="af111-122">Du kan skicka den från en åtgärd till en annan åtgärd eller använda den med `let` nyckelordet för att definiera en ny variabel.</span><span class="sxs-lookup"><span data-stu-id="af111-122">You can pass it from an operation to another operation or use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="af111-123">Den här metoden gör det möjligt att representera klassisk beräkning som samverkar med Quantum-åtgärder på låg nivå, t. ex. i [upptätad kod](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding):</span><span class="sxs-lookup"><span data-stu-id="af111-123">This approach allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding):</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> <span data-ttu-id="af111-124">Varje åtgärd i Q# tar exakt en indata och returnerar exakt en utdata.</span><span class="sxs-lookup"><span data-stu-id="af111-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="af111-125">Flera indata och utdata representeras med hjälp av *tupler*, som samlar in flera värden i ett enda värde.</span><span class="sxs-lookup"><span data-stu-id="af111-125">Multiple inputs and outputs are represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="af111-126">I detta hänseende Q# är ett "tupel-in-tupel"-språk.</span><span class="sxs-lookup"><span data-stu-id="af111-126">In this regard, Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="af111-127">Efter det här konceptet måste en uppsättning tomma parenteser `()` läsas som "Empty"-tupel, som har typen `Unit` .</span><span class="sxs-lookup"><span data-stu-id="af111-127">Following this concept, a set of empty parentheses, `()`, should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="af111-128">Kontrollerade och närliggande aktiviteter</span><span class="sxs-lookup"><span data-stu-id="af111-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="af111-129">Om en åtgärd implementerar en enhetlig omvandling, vilket är fallet för många åtgärder i Q# , är det möjligt att definiera hur åtgärden fungerar när *adjointed* eller *styrs*.</span><span class="sxs-lookup"><span data-stu-id="af111-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="af111-130">En *angränsande* specialisering av en åtgärd anger hur "invertering" av åtgärden agerar, medan en *kontrollerad* specialisering anger hur en åtgärd agerar när dess program villkoras i tillståndet för en viss Quantum-registrering.</span><span class="sxs-lookup"><span data-stu-id="af111-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="af111-131">Angränsande av Quantum-åtgärder är avgörande för många aspekter av Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="af111-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="af111-132">Ett exempel på en sådan situation som diskuteras tillsammans med en användbar Q# programmerings teknik finns i [Conjugations](#conjugations) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="af111-132">For an example of one such situation discussed alongside a useful Q# programming technique, see [Conjugations](#conjugations) in this article.</span></span> 

<span data-ttu-id="af111-133">Den kontrollerade versionen av en åtgärd är en ny åtgärd som effektivt tillämpar bas åtgärden endast om alla qubits för kontrollen är i ett visst tillstånd.</span><span class="sxs-lookup"><span data-stu-id="af111-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="af111-134">Om kontrollens qubits är i superposition tillämpas bas åtgärden på samma sätt som den aktuella delen av superpositionen.</span><span class="sxs-lookup"><span data-stu-id="af111-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="af111-135">Därmed används kontrollerade åtgärder ofta för att generera entanglement.</span><span class="sxs-lookup"><span data-stu-id="af111-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="af111-136">Naturligt, en *kontrollerad angränsande* specialisering kan också finnas, och ange det kontrollerade programmet för en åtgärd som är intilliggande.</span><span class="sxs-lookup"><span data-stu-id="af111-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="af111-137">Om $U $ är den enhetliga omvandling som implementeras av en åtgärd `U` , `Adjoint U` representerar den enhetliga omvandlingen $U ^ \dagger $, som är den komplexa konjugatet.</span><span class="sxs-lookup"><span data-stu-id="af111-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="af111-138">Genom att använda en åtgärd och sedan dess angränsande status till ett tillstånd blir det oförändrat, vilket visas i det faktum att $UU ^ \dagger = U ^ \dagger U = \id $, identitets mat ris.</span><span class="sxs-lookup"><span data-stu-id="af111-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="af111-139">Den enhetliga representationen av en kontrollerad åtgärd är något mer nyanserade, men du hittar mer information om [Quantum Computing-koncept: flera qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="af111-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="af111-140">I följande avsnitt beskrivs hur du anropar dessa olika specialiseringar i din Q# kod och hur du definierar åtgärder för att stödja dem.</span><span class="sxs-lookup"><span data-stu-id="af111-140">The following section describes how to call these various specializations in your Q# code, and how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="af111-141">Anropar åtgärds-specialiseringar</span><span class="sxs-lookup"><span data-stu-id="af111-141">Calling operation specializations</span></span>

<span data-ttu-id="af111-142">En *Functor* i Q# är en fabrik som definierar en ny åtgärd från en annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="af111-142">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="af111-143">De två standard functors i Q# är `Adjoint` och `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="af111-143">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="af111-144">Functors har åtkomst till implementeringen av bas åtgärden när du definierar implementeringen av den nya åtgärden.</span><span class="sxs-lookup"><span data-stu-id="af111-144">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="af111-145">Det innebär att functors kan utföra mer komplexa funktioner än vanliga funktioner på högre nivå.</span><span class="sxs-lookup"><span data-stu-id="af111-145">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="af111-146">Functors har ingen representation i Q# typ systemet.</span><span class="sxs-lookup"><span data-stu-id="af111-146">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="af111-147">Det är därför inte möjligt att binda dem till en variabel eller skicka dem som argument.</span><span class="sxs-lookup"><span data-stu-id="af111-147">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="af111-148">Använd en Functor genom att använda den för en åtgärd som returnerar en ny åtgärd.</span><span class="sxs-lookup"><span data-stu-id="af111-148">Use a functor by applying it to an operation, which returns a new operation.</span></span>
<span data-ttu-id="af111-149">Om du till exempel använder `Adjoint` Functor till `Y` åtgärden returneras den nya åtgärden `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="af111-149">For example, applying the `Adjoint` functor to the `Y` operation returns the new operation `Adjoint Y`.</span></span> <span data-ttu-id="af111-150">Du kan anropa den nya åtgärden som vilken annan åtgärd som helst.</span><span class="sxs-lookup"><span data-stu-id="af111-150">You can invoke the new operation like any other operation.</span></span>
<span data-ttu-id="af111-151">För att en åtgärd ska stödja programmet för `Adjoint` -eller `Controlled` -functors måste dess returtyp nödvändigt vis vara `Unit` .</span><span class="sxs-lookup"><span data-stu-id="af111-151">For an operation to support the application of the `Adjoint` or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="af111-152">`Adjoint` functor</span><span class="sxs-lookup"><span data-stu-id="af111-152">`Adjoint` functor</span></span>

<span data-ttu-id="af111-153">Därför `Adjoint Y(q1)` tillämpar Functor på `Adjoint` `Y` åtgärden för att generera en ny åtgärd och tillämpar den nya åtgärden i `q1` .</span><span class="sxs-lookup"><span data-stu-id="af111-153">Thus, `Adjoint Y(q1)` applies the `Adjoint` functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="af111-154">Den nya åtgärden har samma signatur och typ som bas åtgärd `Y` .</span><span class="sxs-lookup"><span data-stu-id="af111-154">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="af111-155">I synnerhet stöder den nya åtgärden även `Adjoint` och stöder `Controlled` om och bara om bas åtgärden utfördes.</span><span class="sxs-lookup"><span data-stu-id="af111-155">In particular, the new operation also supports `Adjoint`, and supports `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="af111-156">`Adjoint`Functor är en egen invertering, det vill säga är `Adjoint Adjoint Op` alltid detsamma som `Op` .</span><span class="sxs-lookup"><span data-stu-id="af111-156">The `Adjoint` functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="af111-157">`Controlled` functor</span><span class="sxs-lookup"><span data-stu-id="af111-157">`Controlled` functor</span></span>

<span data-ttu-id="af111-158">På samma sätt `Controlled X(controls, target)` tillämpar `Controlled` Functor på `X` åtgärden för att generera en ny åtgärd och tillämpar den nya åtgärden i `controls` och `target` .</span><span class="sxs-lookup"><span data-stu-id="af111-158">Similarly, `Controlled X(controls, target)` applies the `Controlled` functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="af111-159">I Q# tar kontrollerade versioner alltid en matris med kontroll-qubits, och kontrollen är alltid baserad på alla kontroll qubits som är i beräknings `PauliZ` läge () `One` , $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="af111-159">In Q#, controlled versions always take an array of control qubits, and the controlling is always based on all of the control qubits being in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="af111-160">Kontroll som bygger på andra tillstånd uppnås genom att tillämpa lämplig enhetlig drift till kontrollen qubits före den kontrollerade åtgärden, och sedan använda inversen av den enhetliga åtgärden efter den kontrollerade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="af111-160">Controlling based on other states is achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="af111-161">Om du till exempel använder en `X` åtgärd i en kontroll qubit före och efter en kontrollerad åtgärd, så gör åtgärden att kontrol lera `Zero` status ($ \ket {0} $) för den qubit, att tillämpa en `H` åtgärd före och efter kontroller i `PauliX` `One` tillstånd, d.v.s. eigenvalue för Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $ i stället för `PauliZ` `One` tillstånd.</span><span class="sxs-lookup"><span data-stu-id="af111-161">For example, applying an `X` operation to a control qubit before and after a controlled operation causes the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after controls on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="af111-162">Med ett åtgärds uttryck kan du skapa ett nytt åtgärds uttryck med hjälp av `Controlled` Functor.</span><span class="sxs-lookup"><span data-stu-id="af111-162">Given an operation expression, you can form a new operation expression by using the `Controlled` functor.</span></span>
<span data-ttu-id="af111-163">Signaturen för den nya åtgärden baseras på signaturen för den ursprungliga åtgärden.</span><span class="sxs-lookup"><span data-stu-id="af111-163">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="af111-164">Resultat typen är densamma, men indatatypen är en två tuple med en qubit-matris som innehåller kontrollens qubit (s) som det första elementet och argumenten för den ursprungliga åtgärden som det andra elementet.</span><span class="sxs-lookup"><span data-stu-id="af111-164">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="af111-165">Den nya åtgärden stöder `Controlled` och stöder `Adjoint` om och endast om den ursprungliga åtgärden utfördes.</span><span class="sxs-lookup"><span data-stu-id="af111-165">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="af111-166">Om den ursprungliga åtgärden bara tog ett enda argument, kommer [singleton-tupel](xref:microsoft.quantum.guide.types) att spelas här.</span><span class="sxs-lookup"><span data-stu-id="af111-166">If the original operation took only a single argument, then [singleton tuple equivalence](xref:microsoft.quantum.guide.types) comes into play here.</span></span>
<span data-ttu-id="af111-167">Till exempel `Controlled X` är den kontrollerade versionen av `X` åtgärden.</span><span class="sxs-lookup"><span data-stu-id="af111-167">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="af111-168">`X` har typen `(Qubit => Unit is Adj + Ctl)` , så `Controlled X` har typ `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; på grund av singleton tuple-motsvarigheten är detta samma som `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="af111-168">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="af111-169">Kom ihåg att omsluta motsvarande argument för den kontrollerade versionen av åtgärden inom parentes för att konvertera dem till en tupel om bas åtgärden tog flera argument.</span><span class="sxs-lookup"><span data-stu-id="af111-169">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="af111-170">Till exempel `Controlled Rz` är den kontrollerade versionen av `Rz` åtgärden.</span><span class="sxs-lookup"><span data-stu-id="af111-170">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="af111-171">`Rz` har typen `((Double, Qubit) => Unit is Adj + Ctl)` , så `Controlled Rz` har typen `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="af111-171">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="af111-172">Därför `Controlled Rz(controls, (0.1, target))` är det ett giltigt anrop till `Controlled Rz` (Observera parenteser runt `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="af111-172">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="af111-173">Ett annat exempel `CNOT(control, target)` kan implementeras som `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="af111-173">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="af111-174">Om ett mål ska kontrol leras av två Control qubits (CCNOT), använder du en `Controlled X([control1, control2], target)` instruktion.</span><span class="sxs-lookup"><span data-stu-id="af111-174">If a target should be controlled by two control qubits (CCNOT), use a `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="af111-175">`Controlled`Och `Adjoint` functors återkommer, så det finns ingen skillnad mellan att tillämpa `Controlled Adjoint Op` eller `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="af111-175">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="af111-176">Definiera kontrollerade och intilliggande implementeringar</span><span class="sxs-lookup"><span data-stu-id="af111-176">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="af111-177">I den första åtgärds deklarationen i föregående exempel, åtgärderna `BitFlip` och `DecodeSuperdense` definierades med signaturer `(Qubit => Unit)` respektive `((Qubit, Qubit) => (Result, Result))` .</span><span class="sxs-lookup"><span data-stu-id="af111-177">In the first operation declaration in the previous examples, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="af111-178">Eftersom `DecodeSuperdense` omfattar mätningar är det inte en enhetlig åtgärd och därför kan ingen kontrollerad icke-angränsande specialisering finnas (återkalla det relaterade kravet att en sådan åtgärd returnerar `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="af111-178">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="af111-179">Eftersom `BitFlip` du bara utför den enhetliga <xref:microsoft.quantum.intrinsic.x> åtgärden kan du dock ha definierat den med båda specialiseringarna.</span><span class="sxs-lookup"><span data-stu-id="af111-179">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, you could have defined it with both specializations.</span></span>

<span data-ttu-id="af111-180">I det här avsnittet beskrivs hur du kan ta med specialiseringar i dina Q# Åtgärds deklarationer, vilket ger dem möjlighet att anropas tillsammans med `Adjoint` eller `Controlled` functors.</span><span class="sxs-lookup"><span data-stu-id="af111-180">This section details how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` or `Controlled` functors.</span></span>
<span data-ttu-id="af111-181">För ytterligare information om några av de situationer där det är antingen giltigt eller inte giltigt för att deklarera vissa specialiseringar, se [omständigheter för giltiga definiering av specialiseringar](#circumstances-for-validly-defining-specializations) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="af111-181">For more information about some of the situations in which it is either valid or not valid to declare certain specializations, see [Circumstances for validly defining specializations](#circumstances-for-validly-defining-specializations) in this article.</span></span>

<span data-ttu-id="af111-182">Åtgärds egenskaper definierar vilka typer av functors som du kan tillämpa på den deklarerade åtgärden och vilken inverkan de har.</span><span class="sxs-lookup"><span data-stu-id="af111-182">Operation characteristics define what kinds of functors you can apply to the declared operation, and what effect they have.</span></span> <span data-ttu-id="af111-183">Förekomsten av dessa specialiseringar kan deklareras som en del av åtgärdens signatur, särskilt genom en anteckning med drift egenskaper: `is Adj` , `is Ctl` eller `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="af111-183">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="af111-184">Den faktiska implementeringen av varje specialisering kan antingen *implicit* eller *uttryckligen* definieras.</span><span class="sxs-lookup"><span data-stu-id="af111-184">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="af111-185">Ange implementeringar implicit</span><span class="sxs-lookup"><span data-stu-id="af111-185">Implicitly specifying implementations</span></span>

<span data-ttu-id="af111-186">I det här fallet består bröd texten i åtgärds deklarationen enbart av standard implementeringen.</span><span class="sxs-lookup"><span data-stu-id="af111-186">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="af111-187">Exempel:</span><span class="sxs-lookup"><span data-stu-id="af111-187">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="af111-188">Här genereras motsvarande implementering för varje sådan implicit deklarerad specialisering automatiskt av kompilatorn, som ska utföras om-eller- `Adjoint` `Controlled` functors används.</span><span class="sxs-lookup"><span data-stu-id="af111-188">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="af111-189">Anropet till skulle därför `Adjoint PrepareEntangledPair` leda till att kompileraren implementerar det intilliggande av `CNOT` och sedan det intilliggande `H` .</span><span class="sxs-lookup"><span data-stu-id="af111-189">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="af111-190">Dessa enskilda åtgärder är både egna, så att den resulterande `Adjoint PrepareEntangledPair` åtgärden bara består av att tillämpa `CNOT(here, there)` och sedan `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="af111-190">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="af111-191">Därför kan du använda detta för att skriva `DecodeSuperdense` i föregående exempel mer komprimerings bara, genom att använda det angränsande av `PrepareEntangledPair` för att omvandla Entangled-läget tillbaka till ett unentangled-par med qubits:</span><span class="sxs-lookup"><span data-stu-id="af111-191">Hence you can use this to write the `DecodeSuperdense` in the previous example more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="af111-192">Anteckningen med åtgärds egenskaperna i deklarationen är användbar för att säkerställa att kompileraren automatiskt genererar andra specialiseringar baserat på standard implementeringen.</span><span class="sxs-lookup"><span data-stu-id="af111-192">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="af111-193">Det finns flera viktiga begränsningar att tänka på när du skapar åtgärder för användning med functors.</span><span class="sxs-lookup"><span data-stu-id="af111-193">There are several important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="af111-194">De mest kritiska och specialiseringarna för en åtgärd som använder resultatvärdet för en annan åtgärd *kan inte* genereras automatiskt av kompilatorn, eftersom det är oklart hur du ordnar om instruktionerna i en sådan åtgärd för att få samma effekt.</span><span class="sxs-lookup"><span data-stu-id="af111-194">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="af111-195">Därför är det ofta användbart att uttryckligen ange de olika implementeringarna.</span><span class="sxs-lookup"><span data-stu-id="af111-195">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="af111-196">Ange implementeringar explicit</span><span class="sxs-lookup"><span data-stu-id="af111-196">Explicitly specifying implementations</span></span>

<span data-ttu-id="af111-197">Om kompilatorn inte kan generera implementeringen kan du ange den explicit.</span><span class="sxs-lookup"><span data-stu-id="af111-197">In the case where the compiler cannot generate the implementation, you can specify it explicitly.</span></span> <span data-ttu-id="af111-198">Sådana uttryckliga specialiserings deklarationer kan bestå av ett lämpligt *generations direktiv* eller en användardefinierad implementering.</span><span class="sxs-lookup"><span data-stu-id="af111-198">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="af111-199">Följande är ett fullständigt utbud av möjligheter, med några exempel på explicit specialisering.</span><span class="sxs-lookup"><span data-stu-id="af111-199">Following are the full range of possibilities, with some examples of explicit specialization.</span></span> 


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="af111-200">Explicita specialiserings deklarationer</span><span class="sxs-lookup"><span data-stu-id="af111-200">Explicit specialization declarations</span></span>

<span data-ttu-id="af111-201">Q# åtgärder kan innehålla följande uttryckliga specialiserings deklarationer:</span><span class="sxs-lookup"><span data-stu-id="af111-201">Q# operations can contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="af111-202">`body`Specialiseringen anger implementeringen av åtgärden utan att functors tillämpas.</span><span class="sxs-lookup"><span data-stu-id="af111-202">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="af111-203">`adjoint`Specialiseringen anger implementeringen av åtgärden med `Adjoint` Functor tillämpad.</span><span class="sxs-lookup"><span data-stu-id="af111-203">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="af111-204">`controlled`Specialiseringen anger implementeringen av åtgärden med `Controlled` Functor tillämpad.</span><span class="sxs-lookup"><span data-stu-id="af111-204">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="af111-205">`controlled adjoint`Specialiseringen anger implementeringen av åtgärden med både `Adjoint` och `Controlled` functors tillämpas.</span><span class="sxs-lookup"><span data-stu-id="af111-205">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="af111-206">Den här specialiseringen kan också namnges `adjoint controlled` eftersom de två functorsen går på.</span><span class="sxs-lookup"><span data-stu-id="af111-206">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="af111-207">En åtgärd av typen specialisering består av en specialisering (till exempel `body` eller `adjoint` ) följt av en av:</span><span class="sxs-lookup"><span data-stu-id="af111-207">An operation specialization consists of the specialization tag (for example, `body` or `adjoint`) followed by one of:</span></span>

- <span data-ttu-id="af111-208">En explicit deklaration enligt beskrivningen i följande.</span><span class="sxs-lookup"><span data-stu-id="af111-208">An explicit declaration as described in the following.</span></span>
- <span data-ttu-id="af111-209">Ett *direktiv* som talar om för kompileraren *hur* du genererar specialiseringen, en av:</span><span class="sxs-lookup"><span data-stu-id="af111-209">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="af111-210">`intrinsic`, som anger att mål datorn tillhandahåller specialisering.</span><span class="sxs-lookup"><span data-stu-id="af111-210">`intrinsic`, which indicates that the target machine provides the specialization.</span></span>
  - <span data-ttu-id="af111-211">`distribute`, som används med- `controlled` och- `controlled adjoint` specialiseringarna.</span><span class="sxs-lookup"><span data-stu-id="af111-211">`distribute`, used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="af111-212">När det används med `controlled` anger det att kompilatorn ska beräkna specialiseringen genom att tillämpa `Controlled` på alla åtgärder i `body` .</span><span class="sxs-lookup"><span data-stu-id="af111-212">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="af111-213">När det används med `controlled adjoint` anger det att kompilatorn ska beräkna specialiseringen genom att tillämpa `Controlled` på alla åtgärder i `adjoint` specialiseringen.</span><span class="sxs-lookup"><span data-stu-id="af111-213">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="af111-214">`invert`, som anger att kompilatorn ska beräkna `adjoint` specialiseringen genom att invertera `body` , till exempel återföra ordningen på åtgärder och tillämpa den angränsande till var och en.</span><span class="sxs-lookup"><span data-stu-id="af111-214">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, for example, reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="af111-215">När det används med `adjoint controlled` anger detta att kompilatorn ska beräkna specialiseringen genom att invertera `controlled` specialisering.</span><span class="sxs-lookup"><span data-stu-id="af111-215">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="af111-216">`self`, för att ange att den angränsande specialiseringen är samma som `body` specialiseringen.</span><span class="sxs-lookup"><span data-stu-id="af111-216">`self`, to indicate that the adjoint specialization is the same as the `body` specialization.</span></span>
    <span data-ttu-id="af111-217">Användningen `self` är giltig för- `adjoint` och- `adjoint controlled` specialiseringarna.</span><span class="sxs-lookup"><span data-stu-id="af111-217">Using `self` is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="af111-218">För `adjoint controlled` , `self` förutsätter att `adjoint controlled` specialiseringen är samma som `controlled` specialiseringen.</span><span class="sxs-lookup"><span data-stu-id="af111-218">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="af111-219">`auto`, för att ange att kompilatorn ska välja ett lämpligt direktiv att tillämpa.</span><span class="sxs-lookup"><span data-stu-id="af111-219">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="af111-220">Du kan inte använda `auto` för `body` specialisering.</span><span class="sxs-lookup"><span data-stu-id="af111-220">You cannot use`auto` for the `body` specialization.</span></span>

<span data-ttu-id="af111-221">Direktiven och `auto` alla kräver ett avslutande semikolon `;` .</span><span class="sxs-lookup"><span data-stu-id="af111-221">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="af111-222">`auto`Direktivet matchar följande genererade direktiv om en explicit deklaration av `body` tillhandahålls:</span><span class="sxs-lookup"><span data-stu-id="af111-222">The `auto` directive resolves to the following generated directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="af111-223">`adjoint`Specialiseringen genereras enligt direktivet `invert` .</span><span class="sxs-lookup"><span data-stu-id="af111-223">The `adjoint` specialization generates according to the directive `invert`.</span></span>
- <span data-ttu-id="af111-224">`controlled`Specialiseringen genereras enligt direktivet `distribute` .</span><span class="sxs-lookup"><span data-stu-id="af111-224">The `controlled` specialization generates according to the directive `distribute`.</span></span>
- <span data-ttu-id="af111-225">`adjoint controlled`Specialiseringen genereras enligt direktivet `invert` om en explicit deklaration för `controlled` har givits men inte en för `adjoint` , och `distribute` annars.</span><span class="sxs-lookup"><span data-stu-id="af111-225">The `adjoint controlled` specialization  generates according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="af111-226">Om en åtgärd är självständig kan du uttryckligen ange antingen den angränsande eller den kontrollerade intill-specialiseringen via generations direktivet `self` så att kompilatorn kan använda den informationen i optimerings syfte.</span><span class="sxs-lookup"><span data-stu-id="af111-226">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="af111-227">En specialiserings deklaration som innehåller en användardefinierad implementering består av en argument tupel följt av ett instruktions block med den Q# kod som implementerar specialiseringen.</span><span class="sxs-lookup"><span data-stu-id="af111-227">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="af111-228">I argument listan används för `...` att representera argumenten som har deklarerats för åtgärden som helhet.</span><span class="sxs-lookup"><span data-stu-id="af111-228">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="af111-229">För `body` och ska `adjoint` argument listan alltid vara `(...)` . för och måste `controlled` `adjoint controlled` argument listan vara en symbol som representerar matrisen med kontroll qubits, följt av `...` , inom parentes, till exempel `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="af111-229">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="af111-230">Exempel</span><span class="sxs-lookup"><span data-stu-id="af111-230">Examples</span></span>

<span data-ttu-id="af111-231">En åtgärds deklaration kan vara så enkel som följande, som definierar den primitiva Pauli X-åtgärden:</span><span class="sxs-lookup"><span data-stu-id="af111-231">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="af111-232">Observera att den angränsande av Pauli X-åtgärden definieras med direktivet `self` , eftersom efter definition `X` är en egen invertering.</span><span class="sxs-lookup"><span data-stu-id="af111-232">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="af111-233">I det tidigare `PrepareEntangledPair` exemplet motsvarar koden följande kod som innehåller explicita specialiserings deklarationer:</span><span class="sxs-lookup"><span data-stu-id="af111-233">In the earlier `PrepareEntangledPair` example, the code is equivalent to the following code containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="af111-234">Nyckelordet `auto` anger att kompilatorn ska fastställa hur specialiserings implementeringen ska genereras.</span><span class="sxs-lookup"><span data-stu-id="af111-234">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="af111-235">Användardefinierad specialisering</span><span class="sxs-lookup"><span data-stu-id="af111-235">User-defined specialization implementation</span></span>

<span data-ttu-id="af111-236">Om kompileraren inte kan generera implementeringen för en viss specialisering automatiskt, eller om en effektivare implementering kan ges, kan du definiera implementeringen manuellt.</span><span class="sxs-lookup"><span data-stu-id="af111-236">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then you can manually define the implementation.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="af111-237">I det föregående exemplet `adjoint invert;` anger att den angränsande specialiseringen ska genereras genom att invertera bröd texten och `controlled adjoint invert;` att det visar sig att den kontrollerade angränsande specialiseringen ska genereras genom att den aktuella implementeringen av den kontrollerade specialiseringen inverteras.</span><span class="sxs-lookup"><span data-stu-id="af111-237">In the previous example, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="af111-238">Om en eller flera specialiseringar förutom standard texten måste deklareras explicit måste implementeringen för standard texten omslutas till en lämplig specialiserings deklaration.</span><span class="sxs-lookup"><span data-stu-id="af111-238">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="af111-239">Omständigheter för giltiga definiering av specialiseringar</span><span class="sxs-lookup"><span data-stu-id="af111-239">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="af111-240">Åtgärds deklarationer med angränsande/styrda</span><span class="sxs-lookup"><span data-stu-id="af111-240">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="af111-241">Det är tillåtet att ange en åtgärd utan angränsande eller kontrollerade versioner.</span><span class="sxs-lookup"><span data-stu-id="af111-241">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="af111-242">Till exempel har mått åtgärderna ingen eftersom de inte är inverteras eller kontrollerbara.</span><span class="sxs-lookup"><span data-stu-id="af111-242">For instance, measurement operations have neither because they are not invertible or controllable.</span></span>

<span data-ttu-id="af111-243">En åtgärd stöder- `Adjoint` och `Controlled` functors om dess deklaration innehåller en implicit eller explicit deklaration av respektive specialisering.</span><span class="sxs-lookup"><span data-stu-id="af111-243">An operation supports the `Adjoint` and `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="af111-244">En explicit deklarerad angränsande och kontrollerad specialisering innebär att det finns en angränsande/kontrollerad specialisering.</span><span class="sxs-lookup"><span data-stu-id="af111-244">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="af111-245">För en åtgärd vars brödtext innehåller upprepnings-till-lyckade-slingor, set-instruktioner, mätningar, retur-instruktioner eller anrop till andra åtgärder som inte stöder `Adjoint` Functor, genererar automatiskt en angränsande specialisering efter `invert` eller- `auto` direktivet.</span><span class="sxs-lookup"><span data-stu-id="af111-245">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="af111-246">För en åtgärd vars brödtext innehåller anrop till andra åtgärder som inte stöder Functor går det `Controlled` inte att skapa en kontrollerad specialisering automatiskt efter `distribute` eller- `auto` direktivet.</span><span class="sxs-lookup"><span data-stu-id="af111-246">For an operation whose body contains calls to other operations that do not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="af111-247">Kontrollerat från det intilliggande</span><span class="sxs-lookup"><span data-stu-id="af111-247">Controlled Adjoint</span></span>

<span data-ttu-id="af111-248">Den kontrollerade, intilliggande versionen av en åtgärd anger hur du implementerar en Quantum-kontrollerad version av åtgärdens angränsande.</span><span class="sxs-lookup"><span data-stu-id="af111-248">The controlled adjoint version of an operation specifies how to implement a quantum-controlled version of the adjoint of the operation.</span></span>
<span data-ttu-id="af111-249">Det är tillåtet att ange en åtgärd utan kontrollerad version. till exempel har mått åtgärderna ingen kontrollerad, angränsande version eftersom de varken kan styras eller inverteras.</span><span class="sxs-lookup"><span data-stu-id="af111-249">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="af111-250">En kontrollerad, angränsande specialisering för en åtgärd måste finnas om och endast om både en intilliggande och en kontrollerad specialisering finns.</span><span class="sxs-lookup"><span data-stu-id="af111-250">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="af111-251">I så fall härleds förekomsten av den kontrollerade angränsande specialiseringen.</span><span class="sxs-lookup"><span data-stu-id="af111-251">In that case, the existence of the controlled adjoint specialization is inferred.</span></span> <span data-ttu-id="af111-252">Om ingen implementering uttryckligen definieras genererar kompileringen en lämplig specialisering.</span><span class="sxs-lookup"><span data-stu-id="af111-252">If no implementation is explicitly defined, the compile generates an appropriate specialization.</span></span>

<span data-ttu-id="af111-253">För en åtgärd vars brödtext innehåller anrop till andra åtgärder som inte har en kontrollerad version som inte är en kontrollerad version, så genererar automatiskt en angränsande specialisering efter `invert` , `distribute` , eller- `auto` direktivet.</span><span class="sxs-lookup"><span data-stu-id="af111-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute`, or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="af111-254">Skriv kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="af111-254">Type Compatibility</span></span>

<span data-ttu-id="af111-255">Använd en åtgärd med ytterligare functors som stöds överallt där du använder en åtgärd med färre functors men samma signatur.</span><span class="sxs-lookup"><span data-stu-id="af111-255">Use an operation with additional functors supported anywhere you use an operation with fewer functors but the same signature.</span></span> <span data-ttu-id="af111-256">Använd till exempel en åtgärd av typen `(Qubit => Unit is Adj)` överallt där du använder en åtgärd av typen `(Qubit => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="af111-256">For instance, use an operation of type `(Qubit => Unit is Adj)` anywhere you use an operation of type `(Qubit => Unit)`.</span></span>

<span data-ttu-id="af111-257">Q# är *samvariant* med avseende på anrops bara Retur typer: ett anrop som returnerar en typ `'A` är kompatibelt med ett anrop med samma Indatatyp och en resultat typ som är kompatibel med `'A` .</span><span class="sxs-lookup"><span data-stu-id="af111-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that is compatible with `'A` .</span></span>

<span data-ttu-id="af111-258">Q# är *contravariant* med avseende på indatatyper: ett anrop som använder en typ `'A` som indatamängd är kompatibelt med ett anrop med samma resultat typ och en indatatyp som är kompatibel med `'A` .</span><span class="sxs-lookup"><span data-stu-id="af111-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="af111-259">Det innebär att man får följande definitioner,</span><span class="sxs-lookup"><span data-stu-id="af111-259">That is, given the following definitions,</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="af111-260">Du kan</span><span class="sxs-lookup"><span data-stu-id="af111-260">you can</span></span>

- <span data-ttu-id="af111-261">Anropa funktionen `ConjugateInvertWith` med ett `inner` argument för antingen `Invert` eller `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="af111-261">Invoke the function `ConjugateInvertWith` with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="af111-262">Anropa funktionen `ConjugateUnitaryWith` med ett `inner` argument av `ApplyUnitary` , men inte `Invert` .</span><span class="sxs-lookup"><span data-stu-id="af111-262">Invoke the function `ConjugateUnitaryWith` with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="af111-263">Returnera ett värde av typen `(Qubit[] => Unit is Adj + Ctl)` från `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="af111-263">Return a value of type `(Qubit[] => Unit is Adj + Ctl)` from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af111-264">Q# 0,3 introducerade en betydande skillnad i beteendet för användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="af111-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="af111-265">Användardefinierade typer behandlas som en omsluten version av den underliggande typen, i stället för som en undertyp.</span><span class="sxs-lookup"><span data-stu-id="af111-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="af111-266">Det innebär att det inte går att använda ett värde av en användardefinierad typ där du förväntar dig ett värde av den underliggande typen.</span><span class="sxs-lookup"><span data-stu-id="af111-266">This means that a value of a user-defined type is not usable where you expect a value of the underlying type is.</span></span>


### <a name="conjugations"></a><span data-ttu-id="af111-267">Conjugations</span><span class="sxs-lookup"><span data-stu-id="af111-267">Conjugations</span></span>

<span data-ttu-id="af111-268">Till skillnad från klassiska bitar är det något mer engagerande att frigöra Quantum-minne eftersom qubits kan ha oönskade effekter på den återstående beräkningen om qubits fortfarande är Entangled.</span><span class="sxs-lookup"><span data-stu-id="af111-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="af111-269">Dessa effekter kan undvikas genom att du avregistrerar utförda beräkningar innan du frigör minnet.</span><span class="sxs-lookup"><span data-stu-id="af111-269">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="af111-270">Ett vanligt mönster i Quantum Computing är därför följande:</span><span class="sxs-lookup"><span data-stu-id="af111-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="af111-271">Från och med vår 0,9-version Q# har stöd för en conjugation-instruktion som implementerar föregående omvandling.</span><span class="sxs-lookup"><span data-stu-id="af111-271">Starting with our 0.9 release, Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="af111-272">Med den här instruktionen `ApplyWith` kan åtgärden implementeras på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="af111-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="af111-273">En sådan conjugation-instruktion är mycket mer användbar om de yttre och inre omvandlingarna inte är tillgängliga som åtgärder utan är i stället bekväma att beskriva genom ett block som består av flera instruktioner.</span><span class="sxs-lookup"><span data-stu-id="af111-273">Such a conjugation statement becomes far more useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="af111-274">Den inverterade omvandlingen för de instruktioner som definierats inom blocket genereras automatiskt av kompileraren och körs när Apply-blocket har slutförts.</span><span class="sxs-lookup"><span data-stu-id="af111-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="af111-275">Eftersom alla föränderligt-variabler som används som en del av inom-blocket inte kan bindas om i Apply-blocket, garanteras den genererade omvandlingen som det angränsande av beräkningen i avsnittet-block.</span><span class="sxs-lookup"><span data-stu-id="af111-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="af111-276">Definiera nya funktioner</span><span class="sxs-lookup"><span data-stu-id="af111-276">Defining New Functions</span></span>

<span data-ttu-id="af111-277">Functions är helt deterministiska, klassiska rutiner i Q# , som är distinkta från åtgärder i så att de inte får ha några effekter utöver att beräkna ett utdata-värde.</span><span class="sxs-lookup"><span data-stu-id="af111-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="af111-278">I synnerhet kan funktioner inte anropa åtgärder. agera på, allokera eller låna qubits; exempel på slumpmässiga siffror; eller på annat sätt är beroende av ett tillstånd bortom indatavärdet till en funktion.</span><span class="sxs-lookup"><span data-stu-id="af111-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="af111-279">Som en följd Q# är funktioner *rena*, där de alltid mappar samma indatavärden till samma utdata-värden.</span><span class="sxs-lookup"><span data-stu-id="af111-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="af111-280">Det här beteendet gör det möjligt Q# för kompileraren att på ett säkert sätt ändra ordning på hur och när du ska anropa funktioner när du genererar specialisering</span><span class="sxs-lookup"><span data-stu-id="af111-280">This behavior allows the Q# compiler to safely reorder how and when to call functions when generating operation specializations.</span></span>

<span data-ttu-id="af111-281">Varje Q# källfil kan definiera valfritt antal funktioner.</span><span class="sxs-lookup"><span data-stu-id="af111-281">Each Q# source file can define any number of functions.</span></span>
<span data-ttu-id="af111-282">Funktions namn måste vara unika inom ett namn område och får inte stå i konflikt med åtgärds-eller typnamn.</span><span class="sxs-lookup"><span data-stu-id="af111-282">Function names must be unique within a namespace and cannot conflict with operation or type names.</span></span>

<span data-ttu-id="af111-283">Att definiera en funktion fungerar på samma sätt för att definiera en åtgärd, förutom att inga angränsande eller kontrollerade specialiseringar kan definieras för en funktion.</span><span class="sxs-lookup"><span data-stu-id="af111-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="af111-284">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="af111-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="af111-285">eller</span><span class="sxs-lookup"><span data-stu-id="af111-285">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="af111-286">Klassisk logik i functions = = Hej</span><span class="sxs-lookup"><span data-stu-id="af111-286">Classical logic in functions == good</span></span>

<span data-ttu-id="af111-287">När det är möjligt är det bra att skriva ut klassisk logik i termer av funktioner i stället för åtgärder så att åtgärder kan användas mer.</span><span class="sxs-lookup"><span data-stu-id="af111-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations so that operations can more readily use it.</span></span> <span data-ttu-id="af111-288">Om du till exempel hade skrivit den tidigare `Square` deklarationen som en *åtgärd*skulle kompileraren inte ha kunnat garantera att anropet till den med samma indata skulle skapa samma utdata konsekvent.</span><span class="sxs-lookup"><span data-stu-id="af111-288">For example, if you had written the earlier `Square` declaration as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="af111-289">Om du vill ta del av skillnaden mellan Functions och åtgärder kan du tänka på problemet med att slumpmässigt sampla ett slumpmässigt nummer i en Q# åtgärd:</span><span class="sxs-lookup"><span data-stu-id="af111-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="af111-290">Varje tid som `U` anropas har det en annan åtgärd på `target` .</span><span class="sxs-lookup"><span data-stu-id="af111-290">Each time that `U` is called, it has a different action on `target`.</span></span>
<span data-ttu-id="af111-291">I synnerhet kan kompileraren inte garantera att om du lägger till en `adjoint auto` specialisering-deklaration i `U` fungerar den `U(target); Adjoint U(target);` som identitet (det vill säga som en no-OP).</span><span class="sxs-lookup"><span data-stu-id="af111-291">In particular, the compiler cannot guarantee that if you add an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="af111-292">Detta bryter mot definitionen av det intilliggande som definierats i [vektorer och matriser](xref:microsoft.quantum.concepts.vectors), så att kompileraren automatiskt genererar en angränsande specialisering i en åtgärd där du anropar åtgärden <xref:microsoft.quantum.math.randomreal> skulle bryta de garantier som tillhandahålls av kompilatorn, <xref:microsoft.quantum.math.randomreal> är en åtgärd för vilken det inte finns något angränsande eller styrd version.</span><span class="sxs-lookup"><span data-stu-id="af111-292">This violates the definition of the adjoint defined in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing the compiler to auto-generate an adjoint specialization in an operation where you call the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="af111-293">Å andra sidan tillåter funktions anrop som `Square` är säkra, och är säkra på att kompileraren att den bara behöver bevara indatan för `Square` att hålla dess utdata stabil.</span><span class="sxs-lookup"><span data-stu-id="af111-293">On the other hand, allowing function calls such as `Square` is safe, and assures the compiler that it only needs to preserve the input to `Square` to keep its output stable.</span></span>
<span data-ttu-id="af111-294">Att isolera så mycket klassisk logik som möjligt i functions gör det lätt att återanvända den logiken i andra funktioner och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="af111-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="af111-295">Generisk (typ Parameterad) Callables</span><span class="sxs-lookup"><span data-stu-id="af111-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="af111-296">Många funktioner och åtgärder som du kanske vill definiera är inte tungt förlitade på typerna av deras indata, utan används i stället för att implicit använda sina typer via en annan funktion eller åtgärd.</span><span class="sxs-lookup"><span data-stu-id="af111-296">Many functions and operations that you might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="af111-297">Anta till exempel att *mappnings* konceptet är gemensamt för många funktionella språk; med en Function $f (x) $ och en samling värden $ \{ x_1, x_2, \dots, x_n \} $, returnerar kartan en ny samling $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="af111-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="af111-298">För att implementera detta i Q# , dra nytta av det faktum att funktionerna är första klass.</span><span class="sxs-lookup"><span data-stu-id="af111-298">To implement this in Q#, take advantage of the fact that functions are first class.</span></span>
<span data-ttu-id="af111-299">Här är ett snabbt exempel på `Map` , `T` som använder som plats hållare när du tar reda på vilka typer du behöver.</span><span class="sxs-lookup"><span data-stu-id="af111-299">Here is a quick example of `Map`, using `T` as a placeholder while you figure out what types you need.</span></span>

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="af111-300">Observera att den här funktionen ser mycket likadan ut oavsett vilka faktiska typer som du ersätter i.</span><span class="sxs-lookup"><span data-stu-id="af111-300">Note that this function looks very much the same no matter what actual types you substitute in.</span></span>
<span data-ttu-id="af111-301">En karta från heltal till Paulis, till exempel, ser ut ungefär likadant som en karta från flytt ALS nummer till strängar:</span><span class="sxs-lookup"><span data-stu-id="af111-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="af111-302">I princip kan du skriva en version av `Map` för varje par av typer som du stöter på, men det ger upphov till flera problem.</span><span class="sxs-lookup"><span data-stu-id="af111-302">In principle, you could write a version of `Map` for every pair of types that you encounter, but this introduces several difficulties.</span></span>
<span data-ttu-id="af111-303">Om du till exempel hittar ett fel i `Map` måste du se till att korrigeringen tillämpas enhetligt i alla versioner av `Map` .</span><span class="sxs-lookup"><span data-stu-id="af111-303">For instance, if you find a bug in `Map`, then you must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="af111-304">Om du skapar en ny tupel eller UDT måste du dessutom också skapa en ny `Map` för att gå vidare med den nya typen.</span><span class="sxs-lookup"><span data-stu-id="af111-304">Moreover, if you construct a new tuple or UDT, then you must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="af111-305">Även om det här är ett litet antal sådana funktioner kan det vara orimligt att införa fler och fler funktioner i samma formulär som `Map` , men kostnaden för att introducera nya typer blir orimligt stor i relativt kort ordning.</span><span class="sxs-lookup"><span data-stu-id="af111-305">While this is tractable for a small number of such functions, as you collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="af111-306">Det är dock mycket av detta problem att du inte har gett kompilatorn den information som krävs för att identifiera hur de olika versionerna av `Map` är relaterade.</span><span class="sxs-lookup"><span data-stu-id="af111-306">However, much of this difficulty results from the fact that you have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="af111-307">I praktiken vill du att kompileraren ska behandla `Map` som en typ av matematisk funktion från Q# *typer* till Q# functions.</span><span class="sxs-lookup"><span data-stu-id="af111-307">Effectively, you want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="af111-308">Q# formalizes det här begreppet genom att tillåta att funktioner och åtgärder har *typ parametrar*, samt de vanliga tuple-parametrarna.</span><span class="sxs-lookup"><span data-stu-id="af111-308">Q# formalizes this notion by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="af111-309">I föregående exempel vill du tänka på att `Map` ha typ parametrar `Int, Pauli` i det första fallet och `Double, String` i det andra fallet.</span><span class="sxs-lookup"><span data-stu-id="af111-309">In the previous examples, you wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="af111-310">För det mesta använder du de här typ parametrarna som om de var vanliga typer.</span><span class="sxs-lookup"><span data-stu-id="af111-310">For the most part, use these type parameters as though they were ordinary types.</span></span> <span data-ttu-id="af111-311">Använd värden av typen parametrar för att skapa matriser och tupler, anropa funktioner och åtgärder och tilldela till vanliga variabler eller föränderligt.</span><span class="sxs-lookup"><span data-stu-id="af111-311">Use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="af111-312">Det mest extrema fallet med indirekt beroende är att qubits, där ett Q# program inte kan förlita sig på typen av struktur, `Qubit` men **måste** skicka sådana typer till andra funktioner och funktioner.</span><span class="sxs-lookup"><span data-stu-id="af111-312">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="af111-313">När du återvänder till det tidigare exemplet ser du att `Map` måste ha typ parametrar, en för att representera indata till `fn` och en för att representera utdata från `fn` .</span><span class="sxs-lookup"><span data-stu-id="af111-313">Returning to the earlier example, then, you see that `Map` needs to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="af111-314">I Q# skrivs detta genom att lägga till vinkelparenteser (det vill säga `<>` inte bromsar $ \braket {} $!) efter namnet på en funktion eller åtgärd i dess deklaration, och genom att ange varje typ parameter.</span><span class="sxs-lookup"><span data-stu-id="af111-314">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="af111-315">Namnet på varje typ parameter måste börja med en Ticket `'` , vilket indikerar att det är en typ parameter och inte en vanlig typ (kallas även *konkret* typ).</span><span class="sxs-lookup"><span data-stu-id="af111-315">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="af111-316">Därför `Map` skrivs:</span><span class="sxs-lookup"><span data-stu-id="af111-316">Thus, `Map`, is written:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="af111-317">Observera att definitionen av `Map<'Input, 'Output>` ser ut så mycket som previoius-versionerna.</span><span class="sxs-lookup"><span data-stu-id="af111-317">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the previoius versions.</span></span>
<span data-ttu-id="af111-318">Den enda skillnaden är att du uttryckligen har informerat kompilatorn som `Map` inte är direkt beroende av vad `'Input` och `'Output` är, men fungerar för två typer genom att använda dem indirekt genom `fn` .</span><span class="sxs-lookup"><span data-stu-id="af111-318">The only difference is that you have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="af111-319">När du har definierat `Map<'Input, 'Output>` på det här sättet kan du anropa det som om det var en vanlig funktion:</span><span class="sxs-lookup"><span data-stu-id="af111-319">Once you have defined `Map<'Input, 'Output>` in this way, you can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="af111-320">Att skriva allmänna funktioner och åtgärder är en plats där "tuple-in-tupel" är ett mycket användbart sätt att tänka på Q# funktioner och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="af111-320">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="af111-321">Eftersom varje funktion tar exakt en indata och returnerar exakt en utmatning, matchar en indata typen `'T -> 'U` *all* Q# funktion.</span><span class="sxs-lookup"><span data-stu-id="af111-321">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="af111-322">På samma sätt kan du skicka alla åtgärder till en indatatyp `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="af111-322">Similarly, you can pass any operation to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="af111-323">Som ett andra exempel bör du tänka på utmaningen med att skriva en funktion som returnerar kompositionen av två andra funktioner:</span><span class="sxs-lookup"><span data-stu-id="af111-323">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="af111-324">Här måste du ange exakt vad `A` , `B` och `C` är, och därmed begränsa verktyget för vår nya `Compose` funktion.</span><span class="sxs-lookup"><span data-stu-id="af111-324">Here, you must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="af111-325">Efter alla är det `Compose` bara beroende av `A` , `B` , och `C` *via* `innerFn` och `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="af111-325">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="af111-326">Alternativt kan du lägga till typ parametrar som `Compose` anger att det fungerar för *alla* `A` , `B` och `C` , så länge parametrarna matchar de som förväntas av `innerFn` och `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="af111-326">As an alternative, then, you can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="af111-327">Q#Standard biblioteken tillhandahåller en rad olika typer av parameter åtgärder och funktioner som gör det enklare att uttrycka kontroll flödet.</span><span class="sxs-lookup"><span data-stu-id="af111-327">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="af111-328">Dessa beskrivs ytterligare i [ Q# standard biblioteks guiden](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="af111-328">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="af111-329">Callables som värden i den första klassen</span><span class="sxs-lookup"><span data-stu-id="af111-329">Callables as First-Class Values</span></span>

<span data-ttu-id="af111-330">En viktig teknik för att motivera att kontrol lera flöde och klassisk logik med hjälp av funktioner i stället för åtgärder är att använda samma åtgärder och funktioner i som Q# *första klass*.</span><span class="sxs-lookup"><span data-stu-id="af111-330">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="af111-331">Det innebär att de är varje värde på språket i sin egen rätt.</span><span class="sxs-lookup"><span data-stu-id="af111-331">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="af111-332">Till exempel är följande en perfekt giltig Q# kod, om en liten indirekta:</span><span class="sxs-lookup"><span data-stu-id="af111-332">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="af111-333">Värdet för variabeln `ourH` i föregående kodfragment är sedan åtgärden <xref:microsoft.quantum.intrinsic.h> , så att du kan anropa det värdet som vilken annan åtgärd som helst.</span><span class="sxs-lookup"><span data-stu-id="af111-333">The value of the variable `ourH` in the previous snippet is then the operation <xref:microsoft.quantum.intrinsic.h>, such that you can call that value like any other operation.</span></span>
<span data-ttu-id="af111-334">Med den här möjligheten kan du skriva åtgärder som utför åtgärder som en del av deras indata, vilket utgör koncept för kontroll flöde med högre ordning.</span><span class="sxs-lookup"><span data-stu-id="af111-334">With this ability, you can write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="af111-335">Du kan till exempel föreställa oss en åtgärd genom att använda den två gånger till samma mål-qubit.</span><span class="sxs-lookup"><span data-stu-id="af111-335">For instance, you could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="af111-336">Returnera åtgärder från en funktion</span><span class="sxs-lookup"><span data-stu-id="af111-336">Returning operations from a function</span></span>

<span data-ttu-id="af111-337">Det är viktigt att betona att du även kan returnera åtgärder som en del av utdata, så att du kan isolera vissa typer av klassisk villkorlig logik som en klassisk funktion som returnerar en beskrivning av ett Quantum-program i form av en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="af111-337">It's important to emphasize that you can also return operations as a part of outputs, such that you can isolate some kinds of classical conditional logic as a classical function, which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="af111-338">Ett enkelt exempel är att ta med i exemplet på Teleportion, i vilken parten som tar emot ett tvåsidigt meddelande med två bitar måste använda meddelandet för att avkoda sin qubit till rätt transport tillstånd.</span><span class="sxs-lookup"><span data-stu-id="af111-338">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="af111-339">Du kan skriva detta i termer av en funktion som tar de två klassiska bitarna och returnerar rätt avkodnings åtgärd.</span><span class="sxs-lookup"><span data-stu-id="af111-339">You could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

<span data-ttu-id="af111-340">Den här nya funktionen är en funktion, i den här om du anropar den med samma värden `hereBit` och `thereBit` , så kommer du alltid tillbaka till samma åtgärd.</span><span class="sxs-lookup"><span data-stu-id="af111-340">This new function is indeed a function, in that if you call it with the same values of `hereBit` and `thereBit`, you always get back the same operation.</span></span>
<span data-ttu-id="af111-341">Därför kan avkodaren på ett säkert sätt köras i åtgärder utan att behöva känna till hur avkodnings logiken interagerar med definitionerna för de olika specialiseringarna för åtgärder.</span><span class="sxs-lookup"><span data-stu-id="af111-341">Thus, the decoder can safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="af111-342">Det vill säga att den klassiska logiken i en funktion är isolerad, vilket garanterar att-kompilatorn som funktions anropet kan ordnas om med impunity, så länge som indatamängden bevaras.</span><span class="sxs-lookup"><span data-stu-id="af111-342">That is, the classical logic inside a function is isolated, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="af111-343">Partiellt program</span><span class="sxs-lookup"><span data-stu-id="af111-343">Partial Application</span></span>

<span data-ttu-id="af111-344">Du kan göra mycket mer med funktioner som returnerar åtgärder med hjälp av *partiella program*, där du anger en eller flera delar av indatamängden för en funktion eller åtgärd utan att faktiskt anropa den.</span><span class="sxs-lookup"><span data-stu-id="af111-344">You can do significantly more with functions that return operations by using *partial application*, in which you provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="af111-345">I det tidigare `ApplyTwice` exemplet kan du ange att du inte vill ange, till och med vilken qubit den inmatade åtgärden ska gälla:</span><span class="sxs-lookup"><span data-stu-id="af111-345">In the earlier `ApplyTwice` example, you can indicate that you don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="af111-346">I det här fallet innehåller den lokala variabeln `twiceOp` den delvis tillämpade åtgärden `ApplyTwice(op, _)` , där `_` anger delar av de inmatade värden som ännu inte har angetts.</span><span class="sxs-lookup"><span data-stu-id="af111-346">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where `_` indicates parts of the input that have not yet been specified.</span></span>
<span data-ttu-id="af111-347">När du anropar `twiceOp` Nästa rad skickar du som intill den delvis tillämpade åtgärden alla återstående delar av indatamängden till den ursprungliga åtgärden.</span><span class="sxs-lookup"><span data-stu-id="af111-347">When you call `twiceOp` in the next line, you pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="af111-348">Därför är det tidigare kodfragmentet identiskt med att anropa `ApplyTwice(op, target)` direkt, Spara för att du har infört en ny lokal variabel så att du kan försena anropet samtidigt som du tillhandahåller vissa delar av indatan.</span><span class="sxs-lookup"><span data-stu-id="af111-348">Thus, the previous snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that you have introduced a new local variable so you can delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="af111-349">Eftersom en åtgärd som har tillämpats delvis inte anropas förrän hela indata har angetts, kan du på ett säkert sätt tillämpa åtgärder även inifrån functions.</span><span class="sxs-lookup"><span data-stu-id="af111-349">Since an operation that has been partially applied is not actually called until its entire input has been provided, you can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="af111-350">I princip skulle den klassiska logiken i `SquareOperation` ha varit mycket mer engagerad, men den är fortfarande isolerad från resten av en åtgärd av de garantier som kompileraren kan erbjuda om functions.</span><span class="sxs-lookup"><span data-stu-id="af111-350">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span> <span data-ttu-id="af111-351">Q#Standard biblioteket använder den här metoden i hela för att uttrycka klassiskt kontroll flöde på ett sätt som kan användas av Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="af111-351">The Q# standard library uses this approach throughout for expressing classical control flow in a way that quantum programs can readily use.</span></span>


## <a name="recursion"></a><span data-ttu-id="af111-352">Rekursion</span><span class="sxs-lookup"><span data-stu-id="af111-352">Recursion</span></span>

<span data-ttu-id="af111-353">Q# callables kan vara direkt eller indirekt rekursivt.</span><span class="sxs-lookup"><span data-stu-id="af111-353">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="af111-354">Det vill säga en åtgärd eller funktion kan anropa sig själv, eller så kan den anropa ett annat anrop som direkt eller indirekt anropar den anropande åtgärden.</span><span class="sxs-lookup"><span data-stu-id="af111-354">That is, an operation or function can call itself, or it can call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="af111-355">Det finns två viktiga kommentarer om användningen av rekursion, men:</span><span class="sxs-lookup"><span data-stu-id="af111-355">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="af111-356">Användningen av rekursion i åtgärder är sannolikt att störa vissa optimeringar.</span><span class="sxs-lookup"><span data-stu-id="af111-356">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="af111-357">Den här störningen kan ha en betydande inverkan på körnings tiden för algoritmen.</span><span class="sxs-lookup"><span data-stu-id="af111-357">This interference can have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="af111-358">När det körs på en faktisk Quantum-enhet kan stack utrymmet vara begränsat och så att djup rekursion kan leda till ett körnings fel.</span><span class="sxs-lookup"><span data-stu-id="af111-358">When running on an actual quantum device, stack space might be limited, and so deep recursion can lead to a runtime error.</span></span>
  <span data-ttu-id="af111-359">I synnerhet Q# identifierar kompileraren och körnings miljön inte och optimerar slut för and rekursion.</span><span class="sxs-lookup"><span data-stu-id="af111-359">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="af111-360">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="af111-360">Next steps</span></span>

<span data-ttu-id="af111-361">Lär dig mer om [variabler](xref:microsoft.quantum.guide.variables) i Q# .</span><span class="sxs-lookup"><span data-stu-id="af111-361">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>