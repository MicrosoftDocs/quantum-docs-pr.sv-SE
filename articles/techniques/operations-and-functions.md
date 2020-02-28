---
title: 'Q #-åtgärder och-funktioner'
description: 'Läs mer om åtgärder och funktioner i Q # och hur de används i ett Quantum-program.'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 43f0cf2da192a607e514d0c7de57a9bdd067faf7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907672"
---
# <a name="q-operations-and-functions"></a><span data-ttu-id="e4ef9-103">Q #-åtgärder och-funktioner</span><span class="sxs-lookup"><span data-stu-id="e4ef9-103">Q# Operations and Functions</span></span>

<span data-ttu-id="e4ef9-104">Q #-program består av en eller flera *åtgärder* som beskriver sido effekter i Quantum-åtgärder kan ha på Quantum data och en eller flera *funktioner* som tillåter ändringar i klassiska data.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-104">Q# programs consist of one or more *operations* that describe side effects quantum operations can have on quantum data, and one or more *functions* that allow modifications to classical data.</span></span> <span data-ttu-id="e4ef9-105">Till skillnad från åtgärder används funktioner för att beskriva rent klassiskt beteende och har inga effekter, förutom att använda klassiska utmatnings värden.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-105">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span>

<span data-ttu-id="e4ef9-106">Varje åtgärd som definierats i Q # kan sedan anropa valfritt antal andra åtgärder, inklusive inbyggda, inbyggda åtgärder som definierats av språket.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-106">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="e4ef9-107">Det specifika sätt på vilket dessa inbyggda åtgärder definieras beror på mål datorn.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-107">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span> <span data-ttu-id="e4ef9-108">När de kompileras visas varje åtgärd som en .NET-klass typ som kan tillhandahållas mål datorer.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-108">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="e4ef9-109">Definiera nya åtgärder</span><span class="sxs-lookup"><span data-stu-id="e4ef9-109">Defining New Operations</span></span>

<span data-ttu-id="e4ef9-110">Som beskrivs ovan är det mest grundläggande Bygg blocket av ett Quantum-program som skrivits i Q # en *åtgärd*som antingen kan anropas från klassiska .NET-program, t. ex., med hjälp av en simulator eller andra åtgärder inom Q #.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-110">As described above, the most basic building block of a quantum program written in Q# is an *operation*, which can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="e4ef9-111">Varje åtgärd tar indata, genererar utdata och anger implementeringen för en eller flera åtgärds specialiseringar.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-111">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="e4ef9-112">Följande åtgärd definierar t. ex. endast en fördefinierad specialisering och använder en enda qubit som inmatad, och anropar sedan den inbyggda `X` åtgärden på ingången:</span><span class="sxs-lookup"><span data-stu-id="e4ef9-112">For instance, the following operation defines only a default body specialization and takes a single qubit as its input, then calls the built-in `X` operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="e4ef9-113">Nyckelordet `operation` startar åtgärds definitionen och följs av namnet. här `BitFlip`.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-113">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="e4ef9-114">Därefter definieras indatatypen som `Qubit`, tillsammans med ett namn `target` för att referera till indatamängden i den nya åtgärden.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-114">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="e4ef9-115">På samma sätt definierar `Unit` att åtgärdens utdata är tom.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-115">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="e4ef9-116">Detta används på samma sätt som `void` i C# och andra tvingande språk, och motsvarar `unit` i F# och andra funktionella språk.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-116">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

> [!NOTE]
> <span data-ttu-id="e4ef9-117">Vi kommer att utforska detta i mer detalj nedan, men varje åtgärd i Q # tar exakt en indata och returnerar exakt en utmatning.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-117">We will explore this in more detail below, but each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="e4ef9-118">Flera indata och utdata visas sedan med hjälp av *tupler*, som samlar in flera värden i ett enda värde.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-118">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="e4ef9-119">Vi säger att Q # är ett "tupel-in-tupel"-språk.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-119">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="e4ef9-120">Efter det här konceptet bör `()` läsas som "Empty"-tupel, som har typen `Unit`.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-120">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

<span data-ttu-id="e4ef9-121">I den nya åtgärden kan implementeringen anges direkt i deklarationen om endast implementeringen av standard-specialisering måste anges explicit.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-121">Within the new operation, the implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to be specified explicitly.</span></span> <span data-ttu-id="e4ef9-122">Dessutom är det möjligt att definiera implementeringar av, till exempel en eller flera `functor` åtgärder, enligt nedan.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-122">Additionally, it is possible to define the implementations of, for example, one or more `functor` operations, as elaborated below.</span></span> <span data-ttu-id="e4ef9-123">I exemplet ovan är den enda instruktionen att anropa den inbyggda Q #-åtgärden <xref:microsoft.quantum.intrinsic.x>.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-123">In the example above, the only statement is to call the built-in Q# operation <xref:microsoft.quantum.intrinsic.x>.</span></span>

<span data-ttu-id="e4ef9-124">Åtgärder kan också returnera fler intressanta typer än `Unit`.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-124">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="e4ef9-125">Till exempel returnerar <xref:microsoft.quantum.intrinsic.m>-åtgärden utdata av typen `Result`som representerar att ha utfört ett mått.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-125">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="e4ef9-126">Vi kan antingen skicka utdata från en åtgärd till en annan åtgärd eller använda det med nyckelordet `let` för att definiera en ny variabel.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-126">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>
<!-- Link to UID for superdense conceptual and example documentation. -->
<span data-ttu-id="e4ef9-127">Detta gör det möjligt att representera klassisk beräkning som samverkar med Quantum-åtgärder på låg nivå, till exempel i upptätad kod:</span><span class="sxs-lookup"><span data-stu-id="e4ef9-127">This allows for representing classical computation that interacts with quantum operations at a low level, such as in superdense coding:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a><span data-ttu-id="e4ef9-128">Functors, angränsande och styrd</span><span class="sxs-lookup"><span data-stu-id="e4ef9-128">Functors, adjoint and controlled</span></span>
<span data-ttu-id="e4ef9-129">Om en åtgärd implementerar en enhetlig omvandling, är det möjligt att definiera hur åtgärden fungerar när *adjointed* eller *kontrol leras*.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-129">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="e4ef9-130">En angränsande specialisering av en åtgärd anger hur den fungerar när den körs i omvänd ordning, medan en kontrollerad specialisering anger hur en åtgärd fungerar när den tillämpas på tillståndet för ett Quantum-register.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-130">An adjoint specialization of an operation specifies how it acts when run in reverse, while a controlled specialization specifies how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="e4ef9-131">Förekomsten av dessa specialiseringar kan deklareras som en del av åtgärdens signatur: `is Adj + Ctl` i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-131">The existence of these specializations can be declared as part of the operation signature: `is Adj + Ctl` in the following example.</span></span> <span data-ttu-id="e4ef9-132">Motsvarande implementering för varje sådan implicit deklarerad specialisering genereras sedan av kompileraren.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-132">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> <span data-ttu-id="e4ef9-133">Många åtgärder i Q # representerar våra portar.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-133">Many operations in Q# represent unitary gates.</span></span>
> <span data-ttu-id="e4ef9-134">Om $U $ är den enhetliga porten som representeras av en åtgärd `U``Adjoint U` representerar den enhetliga porten $U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-134">If $U$ is the unitary gate represented by an operation `U`, then `Adjoint U` represents the unitary gate $U^\dagger$.</span></span>

<span data-ttu-id="e4ef9-135">Om implementeringen inte kan genereras av kompilatorn kan den uttryckligen anges.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-135">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="e4ef9-136">Sådana uttryckliga specialiserings deklarationer kan bestå av ett lämpligt generations direktiv eller en användardefinierad implementering.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-136">Such explicit specialization declarations can consist of a suitable generation directive or a user defined implementation.</span></span> <span data-ttu-id="e4ef9-137">Koden i `PrepareEntangledPair` ovan motsvarar exempelvis koden nedan som innehåller explicita specialiserings deklarationer:</span><span class="sxs-lookup"><span data-stu-id="e4ef9-137">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="e4ef9-138">Nyckelordet `auto` anger att kompilatorn ska fastställa hur specialiserings implementeringen ska genereras.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-138">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="e4ef9-139">Om kompileraren inte kan generera implementeringen för en viss specialisering automatiskt, eller om en effektivare implementering kan ges, kan implementeringen också definieras manuellt.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-139">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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
<span data-ttu-id="e4ef9-140">I exemplet ovan anger `adjoint invert;` att den angränsande specialiseringen ska genereras genom att invertera bröd texten och `controlled adjoint invert;` anger att den kontrollerade intilliggande specialiseringen ska genereras genom att den angivna implementeringen av den kontrollerade specialiseringen inverteras.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-140">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="e4ef9-141">Vi kommer att se fler exempel på detta i [kontroll flödet med högre ordning](xref:microsoft.quantum.concepts.control-flow).</span><span class="sxs-lookup"><span data-stu-id="e4ef9-141">We will see more examples of this in [Higher-Order Control Flow](xref:microsoft.quantum.concepts.control-flow).</span></span>

<span data-ttu-id="e4ef9-142">Om du vill anropa en specialisering av en åtgärd använder du `Adjoint` eller `Controlled` nyckelord.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-142">To call a specialization of an operation, use the `Adjoint` or `Controlled` keywords.</span></span>
<span data-ttu-id="e4ef9-143">Exemplet över upptätt kodning ovan kan skrivas mer komprimerat genom att använda det angränsande `PrepareEntangledPair` för att transformera Entangled-läget till ett unentangled-par med qubits:</span><span class="sxs-lookup"><span data-stu-id="e4ef9-143">For example, the superdense coding example above can be written more compactly by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="e4ef9-144">Det finns ett antal viktiga begränsningar som du bör tänka på när du skapar åtgärder för användning med functors.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-144">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="e4ef9-145">De mest kritiska och specialiseringarna för en åtgärd som använder resultatvärdet för en annan åtgärd kan inte genereras automatiskt av kompilatorn, eftersom det är oklart hur du ordnar om instruktionerna i en sådan åtgärd för att få samma effekt.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-145">Most critically, specializations for an operation that uses the output value of any other operation cannot be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="e4ef9-146">Definiera nya funktioner</span><span class="sxs-lookup"><span data-stu-id="e4ef9-146">Defining New Functions</span></span>

<span data-ttu-id="e4ef9-147">Med hjälp av Q # kan du också definiera *funktioner*som skiljer sig från åtgärder på så sätt att de inte får ha några effekter utöver att beräkna ett utdata-värde.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-147">Q# also allows for defining *functions*, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="e4ef9-148">I synnerhet kan funktioner inte anropa åtgärder, agera på qubits, sampla slumpmässiga tal eller på annat sätt vara beroende av ett tillstånd bortom indatavärdet till en funktion.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-148">In particular, functions cannot call operations, act on qubits, sample random numbers, or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="e4ef9-149">Som en följd är Q #-funktioner *rena*, där de alltid mappar samma indatavärden till samma utdata-värden.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-149">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="e4ef9-150">På så sätt kan Q #-kompilatorn ändra ordning på hur och när-funktioner anropas när de genererar drifts specialiseringar.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-150">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="e4ef9-151">Att definiera en funktion fungerar på samma sätt för att definiera en åtgärd, förutom att inga angränsande eller kontrollerade specialiseringar kan definieras för en funktion.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-151">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="e4ef9-152">Exempel:</span><span class="sxs-lookup"><span data-stu-id="e4ef9-152">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
<span data-ttu-id="e4ef9-153">När det är möjligt är det bra att skriva ut klassisk logik i termer av funktioner i stället för åtgärder, så att den kan användas mer i drift.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-153">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="e4ef9-154">Om vi har skrivit `Square` som en åtgärd, t. ex., skulle kompilatorn inte ha kunnat garantera att anropet till samma indata konsekvent resulterar i samma utdata.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-154">If we had written `Square` as an operation, for example, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="e4ef9-155">Om du vill ta del av skillnaden mellan funktioner och åtgärder bör du tänka på problemet med att slumpmässigt sampla ett slumpmässigt tal från en Q #-åtgärd:</span><span class="sxs-lookup"><span data-stu-id="e4ef9-155">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="e4ef9-156">Varje `U` anropas, kommer den att ha en annan åtgärd på `target`.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-156">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="e4ef9-157">I synnerhet kan kompileraren inte garantera att om vi har lagt till en `adjoint auto` specialisering-deklaration i `U`, så `U(target); Adjoint U(target);` fungerar som identitet (dvs. som No-OP).</span><span class="sxs-lookup"><span data-stu-id="e4ef9-157">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="e4ef9-158">Detta strider mot definitionen av det angränsande som vi såg i [vektorer och matriser](xref:microsoft.quantum.concepts.vectors), till exempel för att automatiskt generera en angränsande specialisering i en åtgärd där vi har anropat åtgärden <xref:microsoft.quantum.math.randomreal> skulle bryta mot de garantier som kompileraren tillhandahåller. <xref:microsoft.quantum.math.randomreal> är en åtgärd för vilken det inte finns något angränsande eller styrd version.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-158">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="e4ef9-159">Å andra sidan är det möjligt att tillåta funktions anrop som `Square` är säkra, eftersom kompileraren kan vara säker på att den bara behöver bevara indata till `Square` för att hålla dess utdata stabil.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-159">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="e4ef9-160">Att isolera så mycket klassisk logik som möjligt i functions gör det lätt att återanvända den logiken i andra funktioner och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-160">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>

## <a name="control-flow"></a><span data-ttu-id="e4ef9-161">Kontrollflöde</span><span class="sxs-lookup"><span data-stu-id="e4ef9-161">Control Flow</span></span>

<span data-ttu-id="e4ef9-162">I en åtgärd eller funktion körs varje instruktion i ordning, på liknande sätt som de flesta vanliga tvingande klassiska språk.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-162">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="e4ef9-163">Det här kontroll flödet kan ändras, men på tre olika sätt:</span><span class="sxs-lookup"><span data-stu-id="e4ef9-163">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="e4ef9-164">`if`-instruktioner</span><span class="sxs-lookup"><span data-stu-id="e4ef9-164">`if` Statements</span></span>
- <span data-ttu-id="e4ef9-165">`for` slingor</span><span class="sxs-lookup"><span data-stu-id="e4ef9-165">`for` Loops</span></span>
- <span data-ttu-id="e4ef9-166">`repeat`-`until`-slingor</span><span class="sxs-lookup"><span data-stu-id="e4ef9-166">`repeat`-`until` Loops</span></span>

<span data-ttu-id="e4ef9-167">Vi kommer att skjuta upp diskussionen av den senare tills vi diskuterar [ru: er-](xref:microsoft.quantum.techniques.qubits#measurements) kretsar.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-167">We defer discussion of the latter until we discuss [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) circuits.</span></span>
<span data-ttu-id="e4ef9-168">`if` och `for` kontroll flödes konstruktioner går det dock bra att känna till de flesta klassiska programmeringsspråk.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-168">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>
<span data-ttu-id="e4ef9-169">I synnerhet kan ett `if`-uttryck ta ett villkor, kan följas av en eller flera `elif`-instruktioner och kan avslutas med en `else`:</span><span class="sxs-lookup"><span data-stu-id="e4ef9-169">In particular, an `if` statement can take a condition, may be followed by one or more `elif` statements, and may end with an `else`:</span></span>

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

<span data-ttu-id="e4ef9-170">På samma sätt visar `for`-slingor iteration över ett heltals intervall eller över elementen i en matris:</span><span class="sxs-lookup"><span data-stu-id="e4ef9-170">Similarly, `for` loops indicate iteration over a range of integers or over the elements of an array:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

<span data-ttu-id="e4ef9-171">Det är viktigt att `for`-slingor och `if`-uttryck även kan användas i åtgärder för vilka specialisering genereras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-171">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="e4ef9-172">I så fall vänder sig den angränsande av en `for`-slinga riktningen och tar det angränsande av varje iteration.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-172">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="e4ef9-173">Det här följer principen "skor-och-SOCKS": om du vill ångra att du kommer igång på SOCKS och sedan skor måste du ångra att sätta på skor och sedan ångra att sätta igång på SOCKS.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-173">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="e4ef9-174">Det fungerar mindre bra om du vill prova och ta din SOCKS medan du fortfarande använder dina skor!</span><span class="sxs-lookup"><span data-stu-id="e4ef9-174">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="operations-and-functions-as-first-class-values"></a><span data-ttu-id="e4ef9-175">Åtgärder och funktioner som värden i den första klassen</span><span class="sxs-lookup"><span data-stu-id="e4ef9-175">Operations and Functions as First-Class Values</span></span>

<span data-ttu-id="e4ef9-176">En viktig teknik för uppföljning av kontroll flöde och klassisk logik med hjälp av funktioner i stället för åtgärder är att använda dessa åtgärder och funktioner i Q # är *första-klass*.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-176">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="e4ef9-177">Det innebär att de är varje värde på språket i sin egen rätt.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-177">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="e4ef9-178">Följande är till exempel en perfekt giltig Q #-kod, om en liten indirekta:</span><span class="sxs-lookup"><span data-stu-id="e4ef9-178">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="e4ef9-179">Värdet för variabeln `ourH` i kodfragmentet ovan är sedan åtgärden <xref:microsoft.quantum.intrinsic.h>, så att vi kan anropa det värdet som vilken annan åtgärd som helst.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-179">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="e4ef9-180">På så sätt kan vi skriva åtgärder som utför åtgärder som en del av deras indata, vilket utgör en högre ordning för kontroll flödes koncept.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-180">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="e4ef9-181">Vi kan till exempel föreställa oss en åtgärd genom att använda den två gånger för samma mål-qubit.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-181">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="e4ef9-182">I det här exemplet `=>` pilen som visas i typen `(Qubit => Unit)` anger att inmatnings fältet `op` är en åtgärd som tar indata av typen `Qubit` och skapar en tom tupel som utdata.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-182">In this example, the `=>` arrow that appears in the type `(Qubit => Unit)` denotes that the input field `op` is an operation which takes as its input the type `Qubit` and produces an empty tuple as its output.</span></span>
<span data-ttu-id="e4ef9-183">Dessutom anger vi egenskaperna för den åtgärds typen som innehåller den information om vilka functors som stöds.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-183">Additionally we specify the characteristics of that operation type, which contain the information about which functors are supported.</span></span>
<span data-ttu-id="e4ef9-184">En åtgärd av typen `(Qubit => Unit)` stöder varken `Adjoint` eller `Controlled` Functor.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-184">An operation of type `(Qubit => Unit)` supports neither the `Adjoint` nor the `Controlled` functor.</span></span> <span data-ttu-id="e4ef9-185">Om vi vill ange att en åtgärd av den typen måste ha stöd för t. ex. `Adjoint` Functor måste vi deklarera den som adjointable.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-185">If we want to indicate that an operation of that type has to support e.g. the `Adjoint` functor, we have to declare it as being adjointable.</span></span> <span data-ttu-id="e4ef9-186">Detta görs med hjälp av antecknings `is Adj` till typen.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-186">This is done by using the annotation `is Adj` to the type.</span></span> <span data-ttu-id="e4ef9-187">På samma sätt anger `(Qubit => Unit is Ctl)` att en åtgärd av den typen stöder `Controlled`-Functor.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-187">Similarly, `(Qubit => Unit is Ctl)` denotes that an operation of that type supports the `Controlled` functor.</span></span> <span data-ttu-id="e4ef9-188">Vi kommer att utforska detta ytterligare när vi diskuterar [typer i Q #](xref:microsoft.quantum.language.type-model) i allmänhet.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-188">We will explore this further when we discuss [types in Q#](xref:microsoft.quantum.language.type-model) more generally.</span></span>

<span data-ttu-id="e4ef9-189">För närvarande betonar vi att vi även kan returnera åtgärder som en del av utdata, så att vi kan isolera vissa typer av klassisk villkorlig logik som en klassisk funktion som returnerar en beskrivning av ett Quantum-program i form av en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-189">For now, we emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="e4ef9-190">Ett enkelt exempel är att ta med i exemplet på Teleportion, i vilken parten som tar emot ett tvåsidigt meddelande med två bitar måste använda meddelandet för att avkoda sin qubit till rätt transport tillstånd.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-190">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="e4ef9-191">Vi kan skriva detta i termer av en funktion som tar de två klassiska bitarna och returnerar rätt avkodnings åtgärd.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-191">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="e4ef9-192">Den här nya funktionen är en funktion, där om vi anropar den med samma värden som `hereBit` och `thereBit`, kommer vi alltid att få tillbaka samma åtgärd.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-192">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="e4ef9-193">Därför kan avkodaren köras inuti åtgärder utan att du behöver tänka på hur avkodnings logiken interagerar med definitionerna för de olika specialiseringarna för åtgärder.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-193">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="e4ef9-194">Det vill säga att vi har isolerat den klassiska logiken i en funktion, vilket garanterar att den kompilerare som funktions anropet kan ordnas om med impunity, så länge som indatamängden bevaras.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-194">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>

<span data-ttu-id="e4ef9-195">Vi kan också behandla funktioner som värden i den första klassen, eftersom vi kommer att se mer information när vi diskuterar [drift-och funktions typer](#operations-and-functions-as-first-class-values).</span><span class="sxs-lookup"><span data-stu-id="e4ef9-195">We can also treat functions as first-class values, as we will see in more detail when we discuss [operations and function types](#operations-and-functions-as-first-class-values).</span></span>

## <a name="partially-applying-operations-and-functions"></a><span data-ttu-id="e4ef9-196">Delvis tillämpade åtgärder och funktioner</span><span class="sxs-lookup"><span data-stu-id="e4ef9-196">Partially Applying Operations and Functions</span></span>

<span data-ttu-id="e4ef9-197">Vi kan göra mycket mer med funktioner som returnerar åtgärder med hjälp av *partiella program*, där vi kan tillhandahålla en eller flera delar av indatamängden för en funktion eller åtgärd utan att faktiskt anropa det.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-197">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="e4ef9-198">Om du till exempel återkallar `ApplyTwice` exemplet ovan kan vi indikera att vi inte vill ange, till och med vilken qubit den inmatade åtgärden ska gälla:</span><span class="sxs-lookup"><span data-stu-id="e4ef9-198">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="e4ef9-199">I det här fallet har den lokala variabeln `twiceOp` den delvis tillämpade åtgärden `ApplyTwice(op, _)`, där delar av de inmatade värden som ännu inte har angetts anges av `_`.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-199">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="e4ef9-200">När vi faktiskt kallar `twiceOp` på nästa rad, skickar vi som intill den delvis tillämpade åtgärden alla återstående delar av indatamängden till den ursprungliga åtgärden.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-200">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="e4ef9-201">Därför är ovanstående kodfragment detsamma som att ha anropat `ApplyTwice(op, target)` direkt, och spara för att vi har introducerat en ny lokal variabel som gör det möjligt för oss att försena samtalet samtidigt som du tillhandahåller vissa delar av indatan.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-201">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="e4ef9-202">Eftersom en åtgärd som har tillämpats delvis inte anropas förrän hela indatan har tillhandahållits, kan vi på ett säkert sätt tillämpa åtgärder även inifrån functions.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-202">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="e4ef9-203">I princip skulle den klassiska logiken i `SquareOperation` ha varit mycket mer involverad, men den är fortfarande isolerad från resten av en åtgärd av de garantier som kompileraren kan erbjuda om functions.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-203">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="e4ef9-204">Den här metoden kommer att användas i ett standard bibliotek i Q # för att uttrycka klassiskt kontroll flöde på ett sätt som kan användas i Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="e4ef9-204">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>
