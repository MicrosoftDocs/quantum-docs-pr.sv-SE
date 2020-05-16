---
title: 'Åtgärder och funktioner i Q #'
description: Så här definierar och anropar du åtgärder och funktioner, och de kontrollerade och angränsande drifts specialiseringarna.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: bc9695b85b68807801225ccbc903a4622b450768
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431078"
---
# <a name="operations-and-functions-in-q"></a><span data-ttu-id="319e5-103">Åtgärder och funktioner i Q #</span><span class="sxs-lookup"><span data-stu-id="319e5-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="319e5-104">Definiera nya åtgärder</span><span class="sxs-lookup"><span data-stu-id="319e5-104">Defining New Operations</span></span>

<span data-ttu-id="319e5-105">Åtgärder är kärnan i Q #.</span><span class="sxs-lookup"><span data-stu-id="319e5-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="319e5-106">När de har deklarerats kan de antingen anropas från klassiska .NET-program, t. ex. genom att använda en simulator eller andra åtgärder inom Q #.</span><span class="sxs-lookup"><span data-stu-id="319e5-106">Once declared, they can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="319e5-107">Varje åtgärd som definierats i Q # kan sedan anropa valfritt antal andra åtgärder, inklusive inbyggda, inbyggda åtgärder som definierats av språket.</span><span class="sxs-lookup"><span data-stu-id="319e5-107">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="319e5-108">Det specifika sätt på vilket dessa inbyggda åtgärder definieras beror på mål datorn.</span><span class="sxs-lookup"><span data-stu-id="319e5-108">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span>
<span data-ttu-id="319e5-109">När de kompileras visas varje åtgärd som en .NET-klass typ som kan tillhandahållas mål datorer.</span><span class="sxs-lookup"><span data-stu-id="319e5-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="319e5-110">Varje Q #-källfil kan definiera valfritt antal åtgärder.</span><span class="sxs-lookup"><span data-stu-id="319e5-110">Each Q# source file may define any number of operations.</span></span>
<span data-ttu-id="319e5-111">Åtgärds namn måste vara unika inom ett namn område och får inte stå i konflikt med typ-eller funktions namn.</span><span class="sxs-lookup"><span data-stu-id="319e5-111">Operation names must be unique within a namespace and may not conflict with type or function names.</span></span>

<span data-ttu-id="319e5-112">En åtgärds deklaration består av nyckelordet `operation` följt av symbolen som är åtgärdens namn, en typ av identifierare som definierar argumenten för åtgärden, ett kolon `:` , en typ anteckning som beskriver åtgärdens resultat typ, eventuellt en anteckning med åtgärds egenskaper, en öppen klammer `{` , bröd texten i åtgärds deklarationen och en avslutande klammerparentes `}` .</span><span class="sxs-lookup"><span data-stu-id="319e5-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="319e5-113">Varje åtgärd tar indata, genererar utdata och anger implementeringen för en eller flera åtgärds specialiseringar.</span><span class="sxs-lookup"><span data-stu-id="319e5-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="319e5-114">De möjliga specialiseringarna och hur du definierar/anropar dem beskrivs nedan.</span><span class="sxs-lookup"><span data-stu-id="319e5-114">The possible specializations, and how to define/call them, are detailed further below.</span></span>
<span data-ttu-id="319e5-115">I den här övningen ska du ta hänsyn till följande åtgärd, som endast definierar en fördefinierad specialisering och använder en enda qubit som inmatad, och anropar sedan den inbyggda <xref:microsoft.quantum.intrinsic.x> åtgärden för inaktuella ingången:</span><span class="sxs-lookup"><span data-stu-id="319e5-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="319e5-116">Nyckelordet `operation` inleder åtgärds definitionen och följs av namnet. här, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="319e5-116">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="319e5-117">Därefter definieras indatatypen som `Qubit` , tillsammans med ett namn som `target` refererar till indatamängden i den nya åtgärden.</span><span class="sxs-lookup"><span data-stu-id="319e5-117">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="319e5-118">På samma sätt `Unit` definierar den att åtgärdens utdata är tom.</span><span class="sxs-lookup"><span data-stu-id="319e5-118">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="319e5-119">Detta används på samma sätt som `void` i C# och andra tvingande språk och motsvarar `unit` i F # och andra funktionella språk.</span><span class="sxs-lookup"><span data-stu-id="319e5-119">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="319e5-120">Åtgärder kan också returnera fler intressanta typer än `Unit` .</span><span class="sxs-lookup"><span data-stu-id="319e5-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="319e5-121">Till exempel <xref:microsoft.quantum.intrinsic.m> returnerar åtgärden utdata av typen `Result` , vilket representerar att ha utfört ett mått.</span><span class="sxs-lookup"><span data-stu-id="319e5-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="319e5-122">Vi kan antingen skicka utdata från en åtgärd till en annan åtgärd eller använda det med `let` nyckelordet för att definiera en ny variabel.</span><span class="sxs-lookup"><span data-stu-id="319e5-122">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="319e5-123">Detta gör det möjligt att representera klassisk beräkning som samverkar med Quantum-åtgärder på låg nivå, till exempel i [upptätad kod](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span><span class="sxs-lookup"><span data-stu-id="319e5-123">This allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

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
> <span data-ttu-id="319e5-124">Varje åtgärd i Q # tar exakt en indata och returnerar exakt en utmatning.</span><span class="sxs-lookup"><span data-stu-id="319e5-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="319e5-125">Flera indata och utdata visas sedan med hjälp av *tupler*, som samlar in flera värden i ett enda värde.</span><span class="sxs-lookup"><span data-stu-id="319e5-125">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="319e5-126">Vi säger att Q # är ett "tupel-in-tupel"-språk.</span><span class="sxs-lookup"><span data-stu-id="319e5-126">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="319e5-127">Följande begrepp `()` bör sedan läsas som "Empty"-tupel, som har typen `Unit` .</span><span class="sxs-lookup"><span data-stu-id="319e5-127">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>


## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="319e5-128">Kontrollerade och närliggande aktiviteter</span><span class="sxs-lookup"><span data-stu-id="319e5-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="319e5-129">Om en åtgärd implementerar en enhetlig omvandling, vilket är fallet för många åtgärder i Q #, är det möjligt att definiera hur åtgärden fungerar när *adjointed* eller *styrs*.</span><span class="sxs-lookup"><span data-stu-id="319e5-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="319e5-130">En *angränsande* specialisering av en åtgärd anger hur "invertering" av åtgärden agerar, medan en *kontrollerad* specialisering anger hur en åtgärd agerar när dess program villkoras i tillståndet för en viss Quantum-registrering.</span><span class="sxs-lookup"><span data-stu-id="319e5-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="319e5-131">Angränsande av Quantum-åtgärder är avgörande för många aspekter av Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="319e5-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="319e5-132">I avsnittet [Conjugations](#conjugations) kan du se en sådan situation som diskuteras tillsammans med en användbar Q # programmerings teknik.</span><span class="sxs-lookup"><span data-stu-id="319e5-132">Further below, in the [Conjugations](#conjugations) section, you will find one such situation discussed alongside a useful Q# programming technique.</span></span>

<span data-ttu-id="319e5-133">Den kontrollerade versionen av en åtgärd är en ny åtgärd som effektivt tillämpar bas åtgärden endast om alla qubits för kontrollen är i ett visst tillstånd.</span><span class="sxs-lookup"><span data-stu-id="319e5-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="319e5-134">Om kontrollens qubits är i superposition tillämpas bas åtgärden på samma sätt som den aktuella delen av superpositionen.</span><span class="sxs-lookup"><span data-stu-id="319e5-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="319e5-135">Därmed används kontrollerade åtgärder ofta för att generera entanglement.</span><span class="sxs-lookup"><span data-stu-id="319e5-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="319e5-136">Naturligt, en *kontrollerad angränsande* specialisering kan också finnas, och ange det kontrollerade programmet för en åtgärd som är intilliggande.</span><span class="sxs-lookup"><span data-stu-id="319e5-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="319e5-137">Om $U $ är den enhetliga omvandling som implementeras av en åtgärd `U` , `Adjoint U` representerar den enhetliga omvandlingen $U ^ \dagger $, som är den komplexa konjugatet.</span><span class="sxs-lookup"><span data-stu-id="319e5-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="319e5-138">Genom att använda en åtgärd och sedan dess angränsande status till ett tillstånd blir det oförändrat, vilket visas i det faktum att $UU ^ \dagger = U ^ \dagger U = \id $, identitets mat ris.</span><span class="sxs-lookup"><span data-stu-id="319e5-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="319e5-139">Den enhetliga representationen av en kontrollerad åtgärd är något mer nyanserade, men du hittar mer information om [Quantum Computing-koncept: flera qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="319e5-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="319e5-140">I följande avsnitt beskrivs hur du anropar dessa olika specialiseringar i din Q #-kod.</span><span class="sxs-lookup"><span data-stu-id="319e5-140">The following section describes how to call these various specializations in your Q# code.</span></span>
<span data-ttu-id="319e5-141">Nedan förklarar vi hur du definierar åtgärder för att stödja dem.</span><span class="sxs-lookup"><span data-stu-id="319e5-141">Below, we detail how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="319e5-142">Anropar åtgärds-specialiseringar</span><span class="sxs-lookup"><span data-stu-id="319e5-142">Calling operation specializations</span></span>

<span data-ttu-id="319e5-143">En *Functor* i Q # är en fabrik som definierar en ny åtgärd från en annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="319e5-143">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="319e5-144">De två standard functors i Q # är `Adjoint` och `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="319e5-144">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="319e5-145">Functors har åtkomst till implementeringen av bas åtgärden när du definierar implementeringen av den nya åtgärden.</span><span class="sxs-lookup"><span data-stu-id="319e5-145">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="319e5-146">Det innebär att functors kan utföra mer komplexa funktioner än vanliga funktioner på högre nivå.</span><span class="sxs-lookup"><span data-stu-id="319e5-146">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="319e5-147">Functors har ingen representation i Q #-typ systemet.</span><span class="sxs-lookup"><span data-stu-id="319e5-147">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="319e5-148">Det är därför inte möjligt att binda dem till en variabel eller skicka dem som argument.</span><span class="sxs-lookup"><span data-stu-id="319e5-148">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="319e5-149">En Functor används genom att tillämpa den på en åtgärd och returnera en ny åtgärd.</span><span class="sxs-lookup"><span data-stu-id="319e5-149">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="319e5-150">Till exempel skrivs åtgärden som resulterar i `Adjoint` att tillämpa Functor på `Y` åtgärden som `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="319e5-150">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="319e5-151">Den nya åtgärden kan sedan anropas som vilken annan åtgärd som helst.</span><span class="sxs-lookup"><span data-stu-id="319e5-151">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="319e5-152">För att en åtgärd ska kunna stödja program av `Adjoint` och/eller `Controlled` functors måste dess returtyp nödvändigt vis vara `Unit` .</span><span class="sxs-lookup"><span data-stu-id="319e5-152">For an operation to support application of the `Adjoint` and/or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="319e5-153">`Adjoint`functor</span><span class="sxs-lookup"><span data-stu-id="319e5-153">`Adjoint` functor</span></span>

<span data-ttu-id="319e5-154">Därmed `Adjoint Y(q1)` använder det intilliggande Functor för `Y` åtgärden för att generera en ny åtgärd och tillämpar den nya åtgärden i `q1` .</span><span class="sxs-lookup"><span data-stu-id="319e5-154">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="319e5-155">Den nya åtgärden har samma signatur och typ som bas åtgärd `Y` .</span><span class="sxs-lookup"><span data-stu-id="319e5-155">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="319e5-156">I synnerhet tillåter den nya åtgärden också `Adjoint` , och kommer att tillåta `Controlled` om och bara om bas åtgärden utfördes.</span><span class="sxs-lookup"><span data-stu-id="319e5-156">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="319e5-157">Det intilliggande Functor är en egen invertering; det vill säga är `Adjoint Adjoint Op` alltid detsamma som `Op` .</span><span class="sxs-lookup"><span data-stu-id="319e5-157">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="319e5-158">`Controlled`functor</span><span class="sxs-lookup"><span data-stu-id="319e5-158">`Controlled` functor</span></span>

<span data-ttu-id="319e5-159">På samma sätt `Controlled X(controls, target)` tillämpar den kontrollerade Functor på `X` åtgärden för att generera en ny åtgärd och tillämpar den nya åtgärden i `controls` och `target` .</span><span class="sxs-lookup"><span data-stu-id="319e5-159">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="319e5-160">I Q # tar kontrollerade versioner alltid en matris med Control-qubits och det angivna läget är alltid för alla kontroll qubits att vara i beräknings `PauliZ` läge () `One` , $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="319e5-160">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="319e5-161">Kontroll som bygger på andra tillstånd kan uppnås genom att tillämpa lämplig enhetlig drift till kontrollen qubits före den kontrollerade åtgärden, och sedan använda inversen av den enhetliga åtgärden efter den kontrollerade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="319e5-161">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="319e5-162">Om du till exempel använder en `X` åtgärd i en kontroll qubit före och efter en kontrollerad åtgärd, kommer åtgärden att kontrol lera `Zero` status ($ \ket {0} $) för den qubit. att tillämpa en `H` åtgärd innan och efter kommer att ha kontroll över `PauliX` `One` statusen, d.v.s. eigenvalue för Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $ i stället för `PauliZ` `One` tillstånd.</span><span class="sxs-lookup"><span data-stu-id="319e5-162">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="319e5-163">Ett nytt åtgärds uttryck kan skapas med hjälp av Functor för ett åtgärds uttryck `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="319e5-163">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="319e5-164">Signaturen för den nya åtgärden baseras på signaturen för den ursprungliga åtgärden.</span><span class="sxs-lookup"><span data-stu-id="319e5-164">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="319e5-165">Resultat typen är densamma, men indatatypen är en två tuple med en qubit-matris som innehåller kontrollens qubit (s) som det första elementet och argumenten för den ursprungliga åtgärden som det andra elementet.</span><span class="sxs-lookup"><span data-stu-id="319e5-165">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="319e5-166">Den nya åtgärden stöder `Controlled` och stöder `Adjoint` om och endast om den ursprungliga åtgärden utfördes.</span><span class="sxs-lookup"><span data-stu-id="319e5-166">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="319e5-167">Om den ursprungliga åtgärden bara tog ett enda argument, kommer singleton-tupel att visas här.</span><span class="sxs-lookup"><span data-stu-id="319e5-167">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="319e5-168">Till exempel `Controlled X` är den kontrollerade versionen av `X` åtgärden.</span><span class="sxs-lookup"><span data-stu-id="319e5-168">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="319e5-169">`X`har typen `(Qubit => Unit is Adj + Ctl)` , så `Controlled X` har typ `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; på grund av singleton tuple-motsvarigheten är detta samma som `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="319e5-169">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="319e5-170">Kom ihåg att omsluta motsvarande argument för den kontrollerade versionen av åtgärden inom parentes för att konvertera dem till en tupel om bas åtgärden tog flera argument.</span><span class="sxs-lookup"><span data-stu-id="319e5-170">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="319e5-171">Till exempel `Controlled Rz` är den kontrollerade versionen av `Rz` åtgärden.</span><span class="sxs-lookup"><span data-stu-id="319e5-171">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="319e5-172">`Rz`har typen `((Double, Qubit) => Unit is Adj + Ctl)` , så `Controlled Rz` har typen `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="319e5-172">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="319e5-173">Därför `Controlled Rz(controls, (0.1, target))` är det ett giltigt anrop till `Controlled Rz` (Observera parenteser runt `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="319e5-173">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="319e5-174">Ett annat exempel `CNOT(control, target)` kan implementeras som `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="319e5-174">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="319e5-175">Om ett mål ska styras av 2 Control qubits (CCNOT) kan vi använda- `Controlled X([control1, control2], target)` instruktionen.</span><span class="sxs-lookup"><span data-stu-id="319e5-175">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="319e5-176">`Controlled`Och `Adjoint` functors återkommer, så det finns ingen skillnad mellan att tillämpa `Controlled Adjoint Op` eller `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="319e5-176">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="319e5-177">Definiera kontrollerade och intilliggande implementeringar</span><span class="sxs-lookup"><span data-stu-id="319e5-177">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="319e5-178">I de första åtgärds deklarations exemplen ovan `BitFlip` har åtgärderna och `DecodeSuperdense` definierats med signaturer respektive `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` .</span><span class="sxs-lookup"><span data-stu-id="319e5-178">In the first operation declaration examples above, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="319e5-179">Eftersom `DecodeSuperdense` omfattar mätningar är det inte en enhetlig åtgärd och därför kan ingen kontrollerad icke-angränsande specialisering finnas (återkalla det relaterade kravet att en sådan åtgärd returnerar `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="319e5-179">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="319e5-180">Men eftersom `BitFlip` bara utför den enda <xref:microsoft.quantum.intrinsic.x> driften kan vi ha definierat det med båda specialiseringarna.</span><span class="sxs-lookup"><span data-stu-id="319e5-180">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, we could have defined it with both specializations.</span></span>

<span data-ttu-id="319e5-181">Här beskrivs hur du kan inkludera förekomst av specialiseringar i dina deklarationer för Q #-åtgärder, vilket ger dem möjlighet att anropas tillsammans med `Adjoint` och/eller `Controlled` functors.</span><span class="sxs-lookup"><span data-stu-id="319e5-181">Here, we detail how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` and/or `Controlled` functors.</span></span>
<span data-ttu-id="319e5-182">[Nedan](#circumstances-for-validly-defining-specializations)beskrivs några av de situationer där det är antingen giltigt eller inte giltigt för att deklarera vissa specialiseringar.</span><span class="sxs-lookup"><span data-stu-id="319e5-182">Further [below](#circumstances-for-validly-defining-specializations), we describe some of the situations in which it is either valid or not valid to declare certain specializations.</span></span>

<span data-ttu-id="319e5-183">Åtgärds egenskaper definierar vilka typer av functors som kan tillämpas på den deklarerade åtgärden och vilken effekt de har.</span><span class="sxs-lookup"><span data-stu-id="319e5-183">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="319e5-184">Förekomsten av dessa specialiseringar kan deklareras som en del av åtgärdens signatur, särskilt genom en anteckning med drift egenskaper: `is Adj` , `is Ctl` eller `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="319e5-184">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="319e5-185">Den faktiska implementeringen av varje specialisering kan antingen *implicit* eller *uttryckligen* definieras.</span><span class="sxs-lookup"><span data-stu-id="319e5-185">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="319e5-186">Ange implementeringar implicit</span><span class="sxs-lookup"><span data-stu-id="319e5-186">Implicitly specifying implementations</span></span>

<span data-ttu-id="319e5-187">I det här fallet består bröd texten i åtgärds deklarationen enbart av standard implementeringen.</span><span class="sxs-lookup"><span data-stu-id="319e5-187">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="319e5-188">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="319e5-188">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="319e5-189">Här genereras motsvarande implementering för varje sådan implicit deklarerad specialisering automatiskt av kompilatorn, som ska utföras om-eller- `Adjoint` `Controlled` functors används.</span><span class="sxs-lookup"><span data-stu-id="319e5-189">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="319e5-190">Anropet till skulle därför `Adjoint PrepareEntangledPair` leda till att kompileraren implementerar det intilliggande av `CNOT` och sedan det intilliggande `H` .</span><span class="sxs-lookup"><span data-stu-id="319e5-190">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="319e5-191">Dessa enskilda åtgärder är både egna, så att den resulterande `Adjoint PrepareEntangledPair` åtgärden bara består av att tillämpa `CNOT(here, there)` och sedan `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="319e5-191">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="319e5-192">Vi kan därför använda detta för att skriva `DecodeSuperdense` exemplet ovan mer komprimerat, genom att använda det angränsande av `PrepareEntangledPair` för att omvandla Entangled-statusen tillbaka till ett unentangled-par med qubits:</span><span class="sxs-lookup"><span data-stu-id="319e5-192">Hence we can use this to write the `DecodeSuperdense` example above more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="319e5-193">Anteckningen med åtgärds egenskaperna i deklarationen är användbar för att säkerställa att kompileraren automatiskt genererar andra specialiseringar baserat på standard implementeringen.</span><span class="sxs-lookup"><span data-stu-id="319e5-193">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="319e5-194">Det finns ett antal viktiga begränsningar som du bör tänka på när du skapar åtgärder för användning med functors.</span><span class="sxs-lookup"><span data-stu-id="319e5-194">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="319e5-195">De mest kritiska och specialiseringarna för en åtgärd som använder resultatvärdet för en annan åtgärd *kan inte* genereras automatiskt av kompilatorn, eftersom det är oklart hur du ordnar om instruktionerna i en sådan åtgärd för att få samma effekt.</span><span class="sxs-lookup"><span data-stu-id="319e5-195">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="319e5-196">Därför är det ofta användbart att uttryckligen ange de olika implementeringarna.</span><span class="sxs-lookup"><span data-stu-id="319e5-196">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="319e5-197">Ange implementeringar explicit</span><span class="sxs-lookup"><span data-stu-id="319e5-197">Explicitly specifying implementations</span></span>

<span data-ttu-id="319e5-198">Om implementeringen inte kan genereras av kompilatorn kan den uttryckligen anges.</span><span class="sxs-lookup"><span data-stu-id="319e5-198">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="319e5-199">Sådana uttryckliga specialiserings deklarationer kan bestå av ett lämpligt *generations direktiv* eller en användardefinierad implementering.</span><span class="sxs-lookup"><span data-stu-id="319e5-199">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="319e5-200">Här ger vi alla möjligheter, med exempel nedan.</span><span class="sxs-lookup"><span data-stu-id="319e5-200">Here we provide the full range of possibilities, with examples following below.</span></span>


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="319e5-201">Explicita specialiserings deklarationer</span><span class="sxs-lookup"><span data-stu-id="319e5-201">Explicit specialization declarations</span></span>

<span data-ttu-id="319e5-202">Q #-åtgärder kan innehålla följande uttryckliga specialiserings deklarationer:</span><span class="sxs-lookup"><span data-stu-id="319e5-202">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="319e5-203">`body`Specialiseringen anger implementeringen av åtgärden utan att functors tillämpas.</span><span class="sxs-lookup"><span data-stu-id="319e5-203">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="319e5-204">`adjoint`Specialiseringen anger implementeringen av åtgärden med `Adjoint` Functor tillämpad.</span><span class="sxs-lookup"><span data-stu-id="319e5-204">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="319e5-205">`controlled`Specialiseringen anger implementeringen av åtgärden med `Controlled` Functor tillämpad.</span><span class="sxs-lookup"><span data-stu-id="319e5-205">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="319e5-206">`controlled adjoint`Specialiseringen anger implementeringen av åtgärden med både `Adjoint` och `Controlled` functors tillämpas.</span><span class="sxs-lookup"><span data-stu-id="319e5-206">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="319e5-207">Den här specialiseringen kan också namnges `adjoint controlled` eftersom de två functorsen går på.</span><span class="sxs-lookup"><span data-stu-id="319e5-207">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="319e5-208">En åtgärds specialisering består av en specialisering (t. ex. `body` , eller `adjoint` osv.) följt av en av följande:</span><span class="sxs-lookup"><span data-stu-id="319e5-208">An operation specialization consists of the specialization tag (e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="319e5-209">En explicit deklaration enligt beskrivningen nedan.</span><span class="sxs-lookup"><span data-stu-id="319e5-209">An explicit declaration as described below.</span></span>
- <span data-ttu-id="319e5-210">Ett *direktiv* som talar om för kompileraren *hur* du genererar specialiseringen, en av:</span><span class="sxs-lookup"><span data-stu-id="319e5-210">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="319e5-211">`intrinsic`, som anger att specialiseringen tillhandahålls av mål datorn.</span><span class="sxs-lookup"><span data-stu-id="319e5-211">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="319e5-212">`distribute`, som kan användas med- `controlled` och- `controlled adjoint` specialiseringarna.</span><span class="sxs-lookup"><span data-stu-id="319e5-212">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="319e5-213">När det används med `controlled` anger det att kompilatorn ska beräkna specialiseringen genom att tillämpa `Controlled` på alla åtgärder i `body` .</span><span class="sxs-lookup"><span data-stu-id="319e5-213">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="319e5-214">När det används med `controlled adjoint` anger det att kompilatorn ska beräkna specialiseringen genom att tillämpa `Controlled` på alla åtgärder i `adjoint` specialiseringen.</span><span class="sxs-lookup"><span data-stu-id="319e5-214">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="319e5-215">`invert`, som anger att kompilatorn ska beräkna `adjoint` specialiseringen genom att invertera `body` , d.v.s. ändra ordningen på åtgärder och tillämpa den angränsande till var och en.</span><span class="sxs-lookup"><span data-stu-id="319e5-215">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="319e5-216">När det används med `adjoint controlled` anger detta att kompilatorn ska beräkna specialiseringen genom att invertera `controlled` specialisering.</span><span class="sxs-lookup"><span data-stu-id="319e5-216">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="319e5-217">`self`, för att ange att den angränsande specialiseringen är samma som `body` specialiseringen.</span><span class="sxs-lookup"><span data-stu-id="319e5-217">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="319e5-218">Detta är giltigt för- `adjoint` och- `adjoint controlled` specialiseringarna.</span><span class="sxs-lookup"><span data-stu-id="319e5-218">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="319e5-219">För `adjoint controlled` , `self` förutsätter att `adjoint controlled` specialiseringen är samma som `controlled` specialiseringen.</span><span class="sxs-lookup"><span data-stu-id="319e5-219">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="319e5-220">`auto`, för att ange att kompilatorn ska välja ett lämpligt direktiv att tillämpa.</span><span class="sxs-lookup"><span data-stu-id="319e5-220">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="319e5-221">`auto`får inte användas för `body` specialisering.</span><span class="sxs-lookup"><span data-stu-id="319e5-221">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="319e5-222">Direktiven och `auto` alla kräver ett avslutande semikolon `;` .</span><span class="sxs-lookup"><span data-stu-id="319e5-222">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="319e5-223">`auto`Direktivet matchar följande generations direktiv om en explicit deklaration av `body` tillhandahålls:</span><span class="sxs-lookup"><span data-stu-id="319e5-223">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="319e5-224">`adjoint`Specialiseringen skapas enligt direktivet `invert` .</span><span class="sxs-lookup"><span data-stu-id="319e5-224">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="319e5-225">`controlled`Specialiseringen skapas enligt direktivet `distribute` .</span><span class="sxs-lookup"><span data-stu-id="319e5-225">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="319e5-226">`adjoint controlled`Specialiseringen skapas enligt direktivet `invert` om en explicit deklaration för `controlled` har givits men inte en för `adjoint` , och `distribute` annars.</span><span class="sxs-lookup"><span data-stu-id="319e5-226">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="319e5-227">Om en åtgärd är självständig kan du uttryckligen ange antingen den angränsande eller den kontrollerade intill-specialiseringen via generations direktivet `self` så att kompilatorn kan använda den informationen i optimerings syfte.</span><span class="sxs-lookup"><span data-stu-id="319e5-227">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="319e5-228">En specialiserings deklaration som innehåller en användardefinierad implementering består av en argument tupel följt av ett instruktions block med den Q #-kod som implementerar specialiseringen.</span><span class="sxs-lookup"><span data-stu-id="319e5-228">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="319e5-229">I argument listan används för `...` att representera argumenten som har deklarerats för åtgärden som helhet.</span><span class="sxs-lookup"><span data-stu-id="319e5-229">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="319e5-230">För `body` och ska `adjoint` argument listan alltid vara `(...)` . för och måste `controlled` `adjoint controlled` argument listan vara en symbol som representerar matrisen med kontroll qubits, följt av `...` , inom parentes, till exempel `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="319e5-230">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="319e5-231">Exempel</span><span class="sxs-lookup"><span data-stu-id="319e5-231">Examples</span></span>

<span data-ttu-id="319e5-232">En åtgärds deklaration kan vara så enkel som följande, som definierar den primitiva Pauli X-åtgärden:</span><span class="sxs-lookup"><span data-stu-id="319e5-232">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="319e5-233">Observera att den angränsande av Pauli X-åtgärden definieras med direktivet `self` , eftersom efter definition `X` är en egen invertering.</span><span class="sxs-lookup"><span data-stu-id="319e5-233">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="319e5-234">Koden `PrepareEntangledPair` ovan motsvarar exempelvis koden nedan med explicita specialiserings deklarationer:</span><span class="sxs-lookup"><span data-stu-id="319e5-234">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="319e5-235">Nyckelordet `auto` anger att kompilatorn ska fastställa hur specialiserings implementeringen ska genereras.</span><span class="sxs-lookup"><span data-stu-id="319e5-235">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="319e5-236">Användardefinierad specialisering</span><span class="sxs-lookup"><span data-stu-id="319e5-236">User-defined specialization implementation</span></span>

<span data-ttu-id="319e5-237">Om kompileraren inte kan generera implementeringen för en viss specialisering automatiskt, eller om en effektivare implementering kan ges, kan implementeringen också definieras manuellt.</span><span class="sxs-lookup"><span data-stu-id="319e5-237">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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
<span data-ttu-id="319e5-238">I exemplet ovan `adjoint invert;` anger att den angränsande specialiseringen ska genereras genom att invertera bröd texten och att `controlled adjoint invert;` det visar sig att den kontrollerade intilliggande specialiseringen ska genereras genom att den angivna implementeringen av den kontrollerade specialisering inverteras.</span><span class="sxs-lookup"><span data-stu-id="319e5-238">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="319e5-239">Om en eller flera specialiseringar förutom standard texten måste deklareras explicit måste implementeringen för standard texten omslutas till en lämplig specialiserings deklaration.</span><span class="sxs-lookup"><span data-stu-id="319e5-239">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="319e5-240">Omständigheter för giltiga definiering av specialiseringar</span><span class="sxs-lookup"><span data-stu-id="319e5-240">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="319e5-241">Åtgärds deklarationer med angränsande/styrda</span><span class="sxs-lookup"><span data-stu-id="319e5-241">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="319e5-242">Det är tillåtet att ange en åtgärd utan angränsande eller kontrollerade versioner.</span><span class="sxs-lookup"><span data-stu-id="319e5-242">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="319e5-243">Till exempel har mått åtgärderna ingen, eftersom de inte är inverteras eller kontrollerbara.</span><span class="sxs-lookup"><span data-stu-id="319e5-243">For instance, measurement operations have neither, because they are not invertible or controllable.</span></span>

<span data-ttu-id="319e5-244">En åtgärd har stöd för `Adjoint` och/eller `Controlled` functors om dess deklaration innehåller en implicit eller explicit deklaration av respektive specialisering.</span><span class="sxs-lookup"><span data-stu-id="319e5-244">An operation supports the `Adjoint` and/or `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="319e5-245">En explicit deklarerad angränsande och kontrollerad specialisering innebär att det finns en angränsande/kontrollerad specialisering.</span><span class="sxs-lookup"><span data-stu-id="319e5-245">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="319e5-246">För en åtgärd vars brödtext innehåller upprepnings-till-lyckade-slingor, set-instruktioner, mätningar, retur-instruktioner eller anrop till andra åtgärder som inte stöder `Adjoint` Functor, genererar automatiskt en angränsande specialisering efter `invert` eller- `auto` direktivet.</span><span class="sxs-lookup"><span data-stu-id="319e5-246">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="319e5-247">För en åtgärd vars brödtext innehåller anrop till andra åtgärder som inte stöder Functor går det `Controlled` inte att skapa en kontrollerad specialisering automatiskt efter `distribute` eller- `auto` direktivet.</span><span class="sxs-lookup"><span data-stu-id="319e5-247">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="319e5-248">Kontrollerat från det intilliggande</span><span class="sxs-lookup"><span data-stu-id="319e5-248">Controlled Adjoint</span></span>

<span data-ttu-id="319e5-249">Den kontrollerade, intilliggande versionen av en åtgärd anger hur en Quantum-kontrollerad version av åtgärdens angränsande funktion implementeras.</span><span class="sxs-lookup"><span data-stu-id="319e5-249">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="319e5-250">Det är tillåtet att ange en åtgärd utan kontrollerad version. till exempel har mått åtgärderna ingen kontrollerad, angränsande version eftersom de varken kan styras eller inverteras.</span><span class="sxs-lookup"><span data-stu-id="319e5-250">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="319e5-251">En kontrollerad, angränsande specialisering för en åtgärd måste finnas om och endast om både en intilliggande och en kontrollerad specialisering finns.</span><span class="sxs-lookup"><span data-stu-id="319e5-251">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="319e5-252">I så fall härleds förekomsten av den kontrollerade angränsande specialiseringen och en lämplig specialisering genereras av kompilatorn om ingen implementering har definierats explicit.</span><span class="sxs-lookup"><span data-stu-id="319e5-252">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="319e5-253">För en åtgärd vars brödtext innehåller anrop till andra åtgärder som inte har en kontrollerad, intilliggande version, genererar automatiskt en angränsande specialisering efter `invert` , `distribute` eller så `auto` är direktivet inte möjligt.</span><span class="sxs-lookup"><span data-stu-id="319e5-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="319e5-254">Skriv kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="319e5-254">Type Compatibility</span></span>

<span data-ttu-id="319e5-255">En åtgärd med ytterligare functors som stöds kan användas överallt där en åtgärd har färre functors men samma signatur förväntas.</span><span class="sxs-lookup"><span data-stu-id="319e5-255">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="319e5-256">Till exempel kan en åtgärd av typen `(Qubit => Unit is Adj)` användas överallt där en åtgärd av typen `(Qubit => Unit)` är förväntad.</span><span class="sxs-lookup"><span data-stu-id="319e5-256">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="319e5-257">Q # är *samvariant* med avseende på anrops bara Retur typer: ett anrop som returnerar en typ `'A` är kompatibelt med ett anrop med samma Indatatyp och en resultat typ som `'A` är kompatibel med.</span><span class="sxs-lookup"><span data-stu-id="319e5-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="319e5-258">Q # är *contravariant* med avseende på indatatyper: ett anrop som tar en typ `'A` som indatatyp är kompatibelt med ett anrop med samma resultat typ och en indatatyp som är kompatibel med `'A` .</span><span class="sxs-lookup"><span data-stu-id="319e5-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="319e5-259">Det innebär att man får följande definitioner:</span><span class="sxs-lookup"><span data-stu-id="319e5-259">That is, given the following definitions:</span></span>

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

<span data-ttu-id="319e5-260">följande är sant:</span><span class="sxs-lookup"><span data-stu-id="319e5-260">the following are true:</span></span>

- <span data-ttu-id="319e5-261">Funktionen `ConjugateInvertWith` kan anropas med ett `inner` argument i antingen `Invert` eller `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="319e5-261">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="319e5-262">Funktionen `ConjugateUnitaryWith` kan anropas med ett `inner` argument av `ApplyUnitary` , men inte `Invert` .</span><span class="sxs-lookup"><span data-stu-id="319e5-262">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="319e5-263">Ett värde av typen `(Qubit[] => Unit is Adj + Ctl)` kan returneras från `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="319e5-263">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="319e5-264">Q # 0,3 introducerade en betydande skillnad i beteendet för användardefinierade typer.</span><span class="sxs-lookup"><span data-stu-id="319e5-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="319e5-265">Användardefinierade typer behandlas som en omsluten version av den underliggande typen, i stället för som en undertyp.</span><span class="sxs-lookup"><span data-stu-id="319e5-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="319e5-266">Det innebär att ett värde för en användardefinierad typ inte kan användas om ett värde av den underliggande typen förväntas.</span><span class="sxs-lookup"><span data-stu-id="319e5-266">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>


### <a name="conjugations"></a><span data-ttu-id="319e5-267">Conjugations</span><span class="sxs-lookup"><span data-stu-id="319e5-267">Conjugations</span></span>

<span data-ttu-id="319e5-268">Till skillnad från klassiska bitar är det något mer engagerande att frigöra Quantum-minne eftersom qubits kan ha oönskade effekter på den återstående beräkningen om qubits fortfarande är Entangled.</span><span class="sxs-lookup"><span data-stu-id="319e5-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="319e5-269">Detta kan undvikas genom att du avregistrerar utförda beräkningar innan du frigör minnet.</span><span class="sxs-lookup"><span data-stu-id="319e5-269">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="319e5-270">Ett vanligt mönster i Quantum Computing är därför följande:</span><span class="sxs-lookup"><span data-stu-id="319e5-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="319e5-271">Från och med vår 0,9-version har vi stöd för en conjugation-instruktion som implementerar omvandlingen ovan.</span><span class="sxs-lookup"><span data-stu-id="319e5-271">Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="319e5-272">Med den här instruktionen `ApplyWith` kan åtgärden implementeras på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="319e5-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="319e5-273">En sådan conjugation-instruktion är självklart mycket mer användbar om den yttre och inre omvandlingen inte är tillgänglig som åtgärder, men är i stället bekvämare att beskriva genom ett block som består av flera instruktioner.</span><span class="sxs-lookup"><span data-stu-id="319e5-273">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="319e5-274">Den inverterade omvandlingen för de instruktioner som definierats inom blocket genereras automatiskt av kompileraren och körs när Apply-blocket har slutförts.</span><span class="sxs-lookup"><span data-stu-id="319e5-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span>
<span data-ttu-id="319e5-275">Eftersom alla föränderligt-variabler som används som en del av inom-blocket inte kan bindas om i Apply-blocket, garanteras den genererade omvandlingen som det angränsande av beräkningen i avsnittet-block.</span><span class="sxs-lookup"><span data-stu-id="319e5-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="319e5-276">Definiera nya funktioner</span><span class="sxs-lookup"><span data-stu-id="319e5-276">Defining New Functions</span></span>

<span data-ttu-id="319e5-277">Functions är helt deterministiska, klassiska rutiner i Q #, som skiljer sig från åtgärder i så att de inte får ha några effekter utöver att beräkna ett utdata-värde.</span><span class="sxs-lookup"><span data-stu-id="319e5-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="319e5-278">I synnerhet kan funktioner inte anropa åtgärder. agera på, allokera eller låna qubits; exempel på slumpmässiga siffror; eller på annat sätt är beroende av ett tillstånd bortom indatavärdet till en funktion.</span><span class="sxs-lookup"><span data-stu-id="319e5-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="319e5-279">Som en följd är Q #-funktioner *rena*, där de alltid mappar samma indatavärden till samma utdata-värden.</span><span class="sxs-lookup"><span data-stu-id="319e5-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="319e5-280">På så sätt kan Q #-kompilatorn ändra ordning på hur och när-funktioner anropas när de genererar drifts specialiseringar.</span><span class="sxs-lookup"><span data-stu-id="319e5-280">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="319e5-281">Varje Q #-källfil kan definiera valfritt antal funktioner.</span><span class="sxs-lookup"><span data-stu-id="319e5-281">Each Q# source file may define any number of functions.</span></span>
<span data-ttu-id="319e5-282">Funktions namn måste vara unika inom ett namn område och kan inte vara i konflikt med åtgärds-eller typnamn.</span><span class="sxs-lookup"><span data-stu-id="319e5-282">Function names must be unique within a namespace and may not conflict with operation or type names.</span></span>

<span data-ttu-id="319e5-283">Att definiera en funktion fungerar på samma sätt för att definiera en åtgärd, förutom att inga angränsande eller kontrollerade specialiseringar kan definieras för en funktion.</span><span class="sxs-lookup"><span data-stu-id="319e5-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="319e5-284">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="319e5-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="319e5-285">eller</span><span class="sxs-lookup"><span data-stu-id="319e5-285">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="319e5-286">Klassisk logik i functions = = Hej</span><span class="sxs-lookup"><span data-stu-id="319e5-286">Classical logic in functions == good</span></span>

<span data-ttu-id="319e5-287">När det är möjligt är det bra att skriva ut klassisk logik i termer av funktioner i stället för åtgärder, så att den kan användas mer i drift.</span><span class="sxs-lookup"><span data-stu-id="319e5-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="319e5-288">Om vi till exempel hade skrivit `Square` deklarationen ovan som en *åtgärd*, skulle kompileraren inte ha kunnat garantera att anropet till den med samma indata skapar samma utdata konsekvent.</span><span class="sxs-lookup"><span data-stu-id="319e5-288">For example, if we had written the `Square` declaration above as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="319e5-289">Om du vill ta del av skillnaden mellan funktioner och åtgärder bör du tänka på problemet med att slumpmässigt sampla ett slumpmässigt tal från en Q #-åtgärd:</span><span class="sxs-lookup"><span data-stu-id="319e5-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="319e5-290">Varje tid som `U` anropas har den en annan åtgärd `target` .</span><span class="sxs-lookup"><span data-stu-id="319e5-290">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="319e5-291">I synnerhet kan kompileraren inte garantera att om vi har lagt till en `adjoint auto` specialisering `U` -deklaration i fungerar den `U(target); Adjoint U(target);` som identitet (det vill säga som en no-OP).</span><span class="sxs-lookup"><span data-stu-id="319e5-291">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="319e5-292">Detta strider mot definitionen av det angränsande som vi såg i [vektorer och matriser](xref:microsoft.quantum.concepts.vectors), till exempel för att automatiskt generera en angränsande specialisering i en åtgärd där vi har anropat åtgärden <xref:microsoft.quantum.math.randomreal> skulle bryta mot de garantier som tillhandahålls av kompilatorn. <xref:microsoft.quantum.math.randomreal> är en åtgärd för vilken det inte finns något angränsande eller styrd version.</span><span class="sxs-lookup"><span data-stu-id="319e5-292">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="319e5-293">Å andra sidan är det möjligt att tillåta funktions anrop som `Square` är säkra, eftersom kompileraren kan vara säker på att den bara behöver bevara indatan för `Square` att hålla dess utdata stabil.</span><span class="sxs-lookup"><span data-stu-id="319e5-293">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="319e5-294">Att isolera så mycket klassisk logik som möjligt i functions gör det lätt att återanvända den logiken i andra funktioner och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="319e5-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="319e5-295">Generisk (typ Parameterad) Callables</span><span class="sxs-lookup"><span data-stu-id="319e5-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="319e5-296">Många funktioner och åtgärder som vi kanske vill definiera stämmer inte överens med typerna av deras indata, utan att bara implicit använda sina typer via en annan funktion eller åtgärd.</span><span class="sxs-lookup"><span data-stu-id="319e5-296">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="319e5-297">Anta till exempel att *mappnings* konceptet är gemensamt för många funktionella språk; med en Function $f (x) $ och en samling värden $ \{ x_1, x_2, \dots, x_n \} $, returnerar kartan en ny samling $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="319e5-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="319e5-298">För att implementera detta i Q # kan vi dra nytta av att funktionerna är första klass.</span><span class="sxs-lookup"><span data-stu-id="319e5-298">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="319e5-299">Låt oss skriva ut ett snabbt exempel på `Map` , med ★ som plats hållare medan vi tar reda på vilka typer vi behöver.</span><span class="sxs-lookup"><span data-stu-id="319e5-299">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="319e5-300">OBS! den här funktionen ser mycket likadan ut oavsett vilka faktiska typer som vi ersätter i.</span><span class="sxs-lookup"><span data-stu-id="319e5-300">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="319e5-301">En karta från heltal till Paulis, till exempel, ser ut ungefär likadant som en karta från flytt ALS nummer till strängar:</span><span class="sxs-lookup"><span data-stu-id="319e5-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="319e5-302">Vi kan i princip skriva en version av `Map` för varje par av typer som vi stöter på, men detta ger ett antal svårigheter.</span><span class="sxs-lookup"><span data-stu-id="319e5-302">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="319e5-303">Om vi till exempel hittar ett fel i `Map` måste vi se till att korrigeringen tillämpas enhetligt i alla versioner av `Map` .</span><span class="sxs-lookup"><span data-stu-id="319e5-303">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="319e5-304">Om vi konstruerar en ny tupel eller UDT, måste du dessutom också skapa en ny `Map` för att gå vidare med den nya typen.</span><span class="sxs-lookup"><span data-stu-id="319e5-304">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="319e5-305">Även om det här är ett litet antal sådana funktioner, och vi samlar in fler och fler funktioner i samma formulär som `Map` , blir kostnaden för att introducera nya typer orimligt stor i relativt kort ordning.</span><span class="sxs-lookup"><span data-stu-id="319e5-305">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="319e5-306">Mycket av detta problem, men från att vi inte har gett kompilatorn den information som krävs för att identifiera hur de olika versionerna av `Map` är relaterade.</span><span class="sxs-lookup"><span data-stu-id="319e5-306">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="319e5-307">Vi vill att kompilatorn ska behandla `Map` som en typ av matematisk funktion från q # *typer* till q # functions.</span><span class="sxs-lookup"><span data-stu-id="319e5-307">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="319e5-308">Den här begreppet är formell genom att tillåta att funktioner och åtgärder har *typ parametrar*, samt deras vanliga tuple-parametrar.</span><span class="sxs-lookup"><span data-stu-id="319e5-308">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="319e5-309">I exemplen ovan vill vi tänka på att `Map` ha typ parametrar `Int, Pauli` i det första fallet och `Double, String` i det andra fallet.</span><span class="sxs-lookup"><span data-stu-id="319e5-309">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="319e5-310">För det mesta kan dessa typ parametrar sedan användas som om de var vanliga: vi använder värden av typen parametrar för att skapa matriser och tupler, anropa funktioner och åtgärder och tilldela till vanliga variabler eller föränderligt.</span><span class="sxs-lookup"><span data-stu-id="319e5-310">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="319e5-311">Det mest extrema fallet med indirekt beroende är att av qubits, där ett Q #-program inte kan förlita sig på typen av struktur `Qubit` , men **måste** skicka sådana typer till andra funktioner och funktioner.</span><span class="sxs-lookup"><span data-stu-id="319e5-311">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="319e5-312">I exemplet ovan kan vi se att vi måste `Map` ha typ parametrar, ett för att representera indata till `fn` och ett som representerar resultatet från `fn` .</span><span class="sxs-lookup"><span data-stu-id="319e5-312">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="319e5-313">I Q # skrivs detta genom att lägga till vinkelparenteser (det vill säga att `<>` inte bromsar $ \braket {} $!) efter namnet på en funktion eller åtgärd i dess deklaration, och genom att ange varje typ parameter.</span><span class="sxs-lookup"><span data-stu-id="319e5-313">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="319e5-314">Namnet på varje typ parameter måste börja med en Ticket `'` , vilket indikerar att det är en typ parameter och inte en vanlig typ (kallas även *konkret* typ).</span><span class="sxs-lookup"><span data-stu-id="319e5-314">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="319e5-315">För `Map` , skriver vi därför:</span><span class="sxs-lookup"><span data-stu-id="319e5-315">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="319e5-316">Observera att definitionen av `Map<'Input, 'Output>` ser ut ungefär likadant ut som de versioner vi skrev ut tidigare.</span><span class="sxs-lookup"><span data-stu-id="319e5-316">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="319e5-317">Den enda skillnaden är att vi uttryckligen har informerat kompilatorn som `Map` inte direkt är beroende av vad `'Input` och `'Output` är, men fungerar för två typer genom att använda dem indirekt genom `fn` .</span><span class="sxs-lookup"><span data-stu-id="319e5-317">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="319e5-318">När vi har definierat `Map<'Input, 'Output>` på det här sättet kan vi anropa det som om det var en vanlig funktion:</span><span class="sxs-lookup"><span data-stu-id="319e5-318">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="319e5-319">Att skriva allmänna funktioner och åtgärder är en plats där "tupel-in-tupel" är ett mycket användbart sätt att tänka på när det gäller Q #-funktioner och-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="319e5-319">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="319e5-320">Eftersom varje funktion tar exakt en indata och returnerar exakt en utdata, matchar en indata av typen `'T -> 'U` *valfri* Q #-funktion.</span><span class="sxs-lookup"><span data-stu-id="319e5-320">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="319e5-321">På samma sätt kan alla åtgärder skickas till inmatad typ `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="319e5-321">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="319e5-322">Som ett andra exempel bör du tänka på utmaningen med att skriva en funktion som returnerar kompositionen av två andra funktioner:</span><span class="sxs-lookup"><span data-stu-id="319e5-322">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="319e5-323">Här måste vi ange exakt vad `A` , `B` och `C` är, och därmed begränsa verktyget för vår nya `Compose` funktion.</span><span class="sxs-lookup"><span data-stu-id="319e5-323">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="319e5-324">Efter alla är det `Compose` bara beroende av `A` , `B` , och `C` *via* `innerFn` och `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="319e5-324">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="319e5-325">Alternativt kan vi lägga till typ parametrar som `Compose` anger att det fungerar för *alla* `A` , `B` och `C` , så länge parametrarna matchar de som förväntas av `innerFn` och `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="319e5-325">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="319e5-326">Standard biblioteken för Q # innehåller en mängd olika typer av typ parametrar och funktioner som gör det lättare att uttrycka ett kontroll flöde med högre ordning.</span><span class="sxs-lookup"><span data-stu-id="319e5-326">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="319e5-327">Dessa beskrivs ytterligare i guiden för [Q # standard library](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="319e5-327">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="319e5-328">Callables som värden i den första klassen</span><span class="sxs-lookup"><span data-stu-id="319e5-328">Callables as First-Class Values</span></span>

<span data-ttu-id="319e5-329">En viktig teknik för uppföljning av kontroll flöde och klassisk logik med hjälp av funktioner i stället för åtgärder är att använda dessa åtgärder och funktioner i Q # är *första-klass*.</span><span class="sxs-lookup"><span data-stu-id="319e5-329">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="319e5-330">Det innebär att de är varje värde på språket i sin egen rätt.</span><span class="sxs-lookup"><span data-stu-id="319e5-330">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="319e5-331">Följande är till exempel en perfekt giltig Q #-kod, om en liten indirekta:</span><span class="sxs-lookup"><span data-stu-id="319e5-331">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="319e5-332">Värdet för variabeln `ourH` i kodfragmentet ovan är sedan åtgärden <xref:microsoft.quantum.intrinsic.h> , så att vi kan anropa det värdet som vilken annan åtgärd som helst.</span><span class="sxs-lookup"><span data-stu-id="319e5-332">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="319e5-333">På så sätt kan vi skriva åtgärder som utför åtgärder som en del av deras indata, vilket utgör en högre ordning för kontroll flödes koncept.</span><span class="sxs-lookup"><span data-stu-id="319e5-333">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="319e5-334">Vi kan till exempel föreställa oss en åtgärd genom att använda den två gånger för samma mål-qubit.</span><span class="sxs-lookup"><span data-stu-id="319e5-334">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="319e5-335">Returnera åtgärder från en funktion</span><span class="sxs-lookup"><span data-stu-id="319e5-335">Returning operations from a function</span></span>

<span data-ttu-id="319e5-336">Vi betonar att vi även kan returnera åtgärder som en del av utdata, så att vi kan isolera vissa typer av klassisk villkorlig logik som en klassisk funktion som returnerar en beskrivning av ett Quantum-program i form av en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="319e5-336">We emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="319e5-337">Ett enkelt exempel är att ta med i exemplet på Teleportion, i vilken parten som tar emot ett tvåsidigt meddelande med två bitar måste använda meddelandet för att avkoda sin qubit till rätt transport tillstånd.</span><span class="sxs-lookup"><span data-stu-id="319e5-337">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="319e5-338">Vi kan skriva detta i termer av en funktion som tar de två klassiska bitarna och returnerar rätt avkodnings åtgärd.</span><span class="sxs-lookup"><span data-stu-id="319e5-338">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="319e5-339">Den här nya funktionen är en funktion, där om vi anropar den med samma värden `hereBit` och `thereBit` , kommer vi alltid att få tillbaka samma åtgärd.</span><span class="sxs-lookup"><span data-stu-id="319e5-339">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="319e5-340">Därför kan avkodaren köras inuti åtgärder utan att du behöver tänka på hur avkodnings logiken interagerar med definitionerna för de olika specialiseringarna för åtgärder.</span><span class="sxs-lookup"><span data-stu-id="319e5-340">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="319e5-341">Det vill säga att vi har isolerat den klassiska logiken i en funktion, vilket garanterar att den kompilerare som funktions anropet kan ordnas om med impunity, så länge som indatamängden bevaras.</span><span class="sxs-lookup"><span data-stu-id="319e5-341">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="319e5-342">Partiellt program</span><span class="sxs-lookup"><span data-stu-id="319e5-342">Partial Application</span></span>

<span data-ttu-id="319e5-343">Vi kan göra mycket mer med funktioner som returnerar åtgärder med hjälp av *partiella program*, där vi kan tillhandahålla en eller flera delar av indatamängden för en funktion eller åtgärd utan att faktiskt anropa det.</span><span class="sxs-lookup"><span data-stu-id="319e5-343">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="319e5-344">Till exempel kan vi, om du `ApplyTwice` vill, anropa exemplet ovan, ange att vi inte vill ange, till och med vilka qubit ingångs åtgärden ska gälla:</span><span class="sxs-lookup"><span data-stu-id="319e5-344">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="319e5-345">I det här fallet innehåller den lokala variabeln `twiceOp` den delvis tillämpade åtgärden `ApplyTwice(op, _)` , där delar av de inmatade värden som ännu inte har angetts anges av `_` .</span><span class="sxs-lookup"><span data-stu-id="319e5-345">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="319e5-346">När vi faktiskt ringer `twiceOp` på nästa rad, skickas som intill den delvis tillämpade åtgärden alla återstående delar av indatamängden till den ursprungliga åtgärden.</span><span class="sxs-lookup"><span data-stu-id="319e5-346">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="319e5-347">Därför är ovanstående kodfragment detsamma som att ha anropat `ApplyTwice(op, target)` direkt, Spara för att vi har infört en ny lokal variabel som gör det möjligt för oss att försena anropet och tillhandahålla vissa delar av indatan.</span><span class="sxs-lookup"><span data-stu-id="319e5-347">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="319e5-348">Eftersom en åtgärd som har tillämpats delvis inte anropas förrän hela indatan har tillhandahållits, kan vi på ett säkert sätt tillämpa åtgärder även inifrån functions.</span><span class="sxs-lookup"><span data-stu-id="319e5-348">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="319e5-349">I princip skulle den klassiska logiken i `SquareOperation` ha varit mycket mer engagerad, men den är fortfarande isolerad från resten av en åtgärd av de garantier som kompileraren kan erbjuda om functions.</span><span class="sxs-lookup"><span data-stu-id="319e5-349">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="319e5-350">Den här metoden kommer att användas i ett standard bibliotek i Q # för att uttrycka klassiskt kontroll flöde på ett sätt som kan användas i Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="319e5-350">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>


## <a name="recursion"></a><span data-ttu-id="319e5-351">Rekursion</span><span class="sxs-lookup"><span data-stu-id="319e5-351">Recursion</span></span>

<span data-ttu-id="319e5-352">Q # callables kan vara direkt eller indirekt rekursivt.</span><span class="sxs-lookup"><span data-stu-id="319e5-352">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="319e5-353">Det vill säga en åtgärd eller funktion kan anropa sig själv, eller så kan den anropa ett annat anrop som direkt eller indirekt anropar den anropande åtgärden.</span><span class="sxs-lookup"><span data-stu-id="319e5-353">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="319e5-354">Det finns två viktiga kommentarer om användningen av rekursion, men:</span><span class="sxs-lookup"><span data-stu-id="319e5-354">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="319e5-355">Användningen av rekursion i åtgärder är sannolikt att störa vissa optimeringar.</span><span class="sxs-lookup"><span data-stu-id="319e5-355">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="319e5-356">Detta kan ha en betydande inverkan på körnings tiden för algoritmen.</span><span class="sxs-lookup"><span data-stu-id="319e5-356">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="319e5-357">Vid körning på en faktisk Quantum-enhet kan stack utrymmet vara begränsat och så att djup rekursion kan leda till ett körnings fel.</span><span class="sxs-lookup"><span data-stu-id="319e5-357">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="319e5-358">I synnerhet identifierar inte Q #-kompilatorn och körnings miljön och optimerar slut rekursion.</span><span class="sxs-lookup"><span data-stu-id="319e5-358">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="whats-next"></a><span data-ttu-id="319e5-359">Vad står på tur?</span><span class="sxs-lookup"><span data-stu-id="319e5-359">What's Next?</span></span>
<span data-ttu-id="319e5-360">Lär dig mer om [variabler](xref:microsoft.quantum.guide.variables) i Q #.</span><span class="sxs-lookup"><span data-stu-id="319e5-360">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>