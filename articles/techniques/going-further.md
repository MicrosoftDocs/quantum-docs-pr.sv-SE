---
title: 'Q #-metoder – gå vidare | Microsoft Docs'
description: 'Q #-tekniker – gå vidare'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: c079364f8808304e0132fa2a4226cd6400e81339
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863154"
---
# <a name="going-further"></a><span data-ttu-id="cc968-103">Gå vidare</span><span class="sxs-lookup"><span data-stu-id="cc968-103">Going Further</span></span> #

<span data-ttu-id="cc968-104">Nu när du har sett hur du skriver intressanta Quantum-program i Q # går det här avsnittet vidare genom att introducera några fler avancerade ämnen som bör vara användbara i framtiden.</span><span class="sxs-lookup"><span data-stu-id="cc968-104">Now that you've seen how to write interesting quantum programs in Q#, this section goes further by introducing a few more advanced topics that should prove useful going forward.</span></span>


## <a name="generic-operations-and-functions"></a><span data-ttu-id="cc968-105">Allmänna åtgärder och funktioner</span><span class="sxs-lookup"><span data-stu-id="cc968-105">Generic Operations and Functions</span></span> ##

> [!TIP]
> <span data-ttu-id="cc968-106">Det här avsnittet förutsätter grundläggande kunskaper om [generiska i C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generiska i F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ mallar](https://docs.microsoft.com/cpp/cpp/templates-cpp)eller liknande metoder för metaprogramming på andra språk.</span><span class="sxs-lookup"><span data-stu-id="cc968-106">This section assumes some basic familiarity with [generics in C#](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generics in F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [C++ templates](https://docs.microsoft.com/cpp/cpp/templates-cpp), or similar approaches to metaprogramming in other languages.</span></span>

<span data-ttu-id="cc968-107">Många funktioner och åtgärder som vi kanske vill definiera stämmer inte överens med typerna av deras indata, utan att bara implicit använda sina typer via en annan funktion eller åtgärd.</span><span class="sxs-lookup"><span data-stu-id="cc968-107">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="cc968-108">Anta till exempel att *mappnings* konceptet är gemensamt för många funktionella språk; med en Function $f (x) $ och en samling värden $\{x_1, x_2, \dots, x_n\}$, returnerar kartan en ny samling $\{f (x_1), f (x_2), \dots, f (x_n)\}$.</span><span class="sxs-lookup"><span data-stu-id="cc968-108">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="cc968-109">För att implementera detta i Q # kan vi dra nytta av att funktionerna är första klass.</span><span class="sxs-lookup"><span data-stu-id="cc968-109">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="cc968-110">Nu ska vi skriva ut ett snabbt exempel på `Map`, med ★ som plats hållare medan vi tar reda på vilka typer vi behöver.</span><span class="sxs-lookup"><span data-stu-id="cc968-110">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="cc968-111">OBS! den här funktionen ser mycket likadan ut oavsett vilka faktiska typer som vi ersätter i.</span><span class="sxs-lookup"><span data-stu-id="cc968-111">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="cc968-112">En karta från heltal till Paulis, till exempel, ser ut ungefär likadant som en karta från flytt ALS nummer till strängar:</span><span class="sxs-lookup"><span data-stu-id="cc968-112">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="cc968-113">Vi kan i princip skriva en version av `Map` för varje par av typer som vi stöter på, men detta ger ett antal svårigheter.</span><span class="sxs-lookup"><span data-stu-id="cc968-113">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="cc968-114">Om vi till exempel upptäcker ett fel i `Map`måste vi se till att korrigeringen tillämpas enhetligt i alla versioner av `Map`.</span><span class="sxs-lookup"><span data-stu-id="cc968-114">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="cc968-115">Om vi konstruerar en ny tupel eller UDT, måste du dessutom också skapa en ny `Map` för att gå vidare med den nya typen.</span><span class="sxs-lookup"><span data-stu-id="cc968-115">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="cc968-116">Även om det här är ett litet antal sådana funktioner, och vi samlar in fler och fler funktioner i samma formulär som `Map`, blir kostnaden för att introducera nya typer orimligt stor i relativt kort ordning.</span><span class="sxs-lookup"><span data-stu-id="cc968-116">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="cc968-117">Mycket av detta problem, men från att vi inte har gett kompilatorn den information som krävs för att identifiera hur de olika versionerna av `Map` är relaterade.</span><span class="sxs-lookup"><span data-stu-id="cc968-117">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="cc968-118">Vi vill att kompilatorn ska behandla `Map` som en typ av matematisk funktion från Q # *typer* till q # functions.</span><span class="sxs-lookup"><span data-stu-id="cc968-118">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>
<span data-ttu-id="cc968-119">Den här begreppet är formell genom att tillåta att funktioner och åtgärder har *typ parametrar*, samt deras vanliga tuple-parametrar.</span><span class="sxs-lookup"><span data-stu-id="cc968-119">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="cc968-120">I exemplen ovan vill vi tänka på `Map` som har typ parametrar `Int, Pauli` i det första fallet och `Double, String` i det andra fallet.</span><span class="sxs-lookup"><span data-stu-id="cc968-120">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="cc968-121">För det mesta kan dessa typ parametrar sedan användas som om de var vanliga: vi använder värden av typen parametrar för att skapa matriser och tupler, anropa funktioner och åtgärder och tilldela till vanliga variabler eller föränderligt.</span><span class="sxs-lookup"><span data-stu-id="cc968-121">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="cc968-122">Det mest extrema fallet med indirekt beroende är att av qubits, där ett Q #-program inte kan förlita sig på strukturen för `Qubit` typen, men **måste** skicka sådana typer till andra funktioner och funktioner.</span><span class="sxs-lookup"><span data-stu-id="cc968-122">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="cc968-123">I exemplet ovan kan vi se att vi behöver `Map` att ha typ parametrar, ett för att representera indata till `fn` och ett för att representera utdata från `fn`.</span><span class="sxs-lookup"><span data-stu-id="cc968-123">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="cc968-124">I Q # skrivs detta genom att lägga till vinkelparenteser (det vill säga `<>`, inte bromsar $ \braket{}$!) efter namnet på en funktion eller åtgärd i dess deklaration, och genom att ange varje typ parameter.</span><span class="sxs-lookup"><span data-stu-id="cc968-124">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="cc968-125">Namnet på varje typ parameter måste börja med en Ticket `'`, vilket indikerar att det är en typ parameter och inte en vanlig typ (kallas även *konkret* typ).</span><span class="sxs-lookup"><span data-stu-id="cc968-125">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="cc968-126">För `Map`skriver vi därför:</span><span class="sxs-lookup"><span data-stu-id="cc968-126">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="cc968-127">Observera att definitionen av `Map<'Input, 'Output>` ser mycket likt de versioner vi skrev ut tidigare.</span><span class="sxs-lookup"><span data-stu-id="cc968-127">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="cc968-128">Den enda skillnaden är att vi uttryckligen har informerat kompilatorn att `Map` inte direkt är beroende av vad `'Input` och `'Output` är, men fungerar för två typer genom att använda dem indirekt via `fn`.</span><span class="sxs-lookup"><span data-stu-id="cc968-128">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="cc968-129">När vi har definierat `Map<'Input, 'Output>` på det här sättet kan vi anropa det som om det var en vanlig funktion:</span><span class="sxs-lookup"><span data-stu-id="cc968-129">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="cc968-130">Att skriva allmänna funktioner och åtgärder är en plats där "tupel-in-tupel" är ett mycket användbart sätt att tänka på när det gäller Q #-funktioner och-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="cc968-130">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="cc968-131">Eftersom varje funktion tar exakt en indata och returnerar exakt en utdata, matchar indata typen `'T -> 'U` *alla* Q #-funktioner.</span><span class="sxs-lookup"><span data-stu-id="cc968-131">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="cc968-132">På samma sätt kan alla åtgärder skickas till inmatade typer `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="cc968-132">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="cc968-133">Som ett andra exempel bör du tänka på utmaningen med att skriva en funktion som returnerar kompositionen av två andra funktioner:</span><span class="sxs-lookup"><span data-stu-id="cc968-133">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="cc968-134">Här måste vi ange exakt vad `A`, `B`och `C` är, vilket begränsar verktyget för vår nya `Compose`-funktion.</span><span class="sxs-lookup"><span data-stu-id="cc968-134">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="cc968-135">Efter allt är `Compose` bara beroende av `A`, `B`och `C` *via* `innerFn` och `outerFn`.</span><span class="sxs-lookup"><span data-stu-id="cc968-135">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="cc968-136">Alternativt kan vi lägga till typ parametrar till `Compose` som anger att det fungerar för *alla* `A`, `B`och `C`, så länge parametrarna matchar de som förväntas av `innerFn` och `outerFn`:</span><span class="sxs-lookup"><span data-stu-id="cc968-136">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="cc968-137">Standard biblioteken för Q # innehåller en mängd olika typer av typ parametrar och funktioner som gör det lättare att uttrycka ett kontroll flöde med högre ordning.</span><span class="sxs-lookup"><span data-stu-id="cc968-137">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="cc968-138">Dessa beskrivs ytterligare i guiden för [Q # standard library](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="cc968-138">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="borrowing-qubits"></a><span data-ttu-id="cc968-139">Låna qubits</span><span class="sxs-lookup"><span data-stu-id="cc968-139">Borrowing Qubits</span></span> ##

<span data-ttu-id="cc968-140">Upplånings metoden gör det möjligt att allokera qubits som kan användas som Scratch-utrymme under en beräkning.</span><span class="sxs-lookup"><span data-stu-id="cc968-140">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span> <span data-ttu-id="cc968-141">Dessa qubits är vanligt vis inte i rent tillstånd, dvs. de är inte nödvändigt vis initierade i ett känt tillstånd som $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="cc968-141">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span> <span data-ttu-id="cc968-142">En pratar också om "smutsig" qubits när deras tillstånd är okänt och kan till och med vara Entangled med andra delar av Quantum-datorns minne.</span><span class="sxs-lookup"><span data-stu-id="cc968-142">One also speaks of "dirty" qubits as their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span> <span data-ttu-id="cc968-143">Bland de kända användnings fallen av smutsig qubits är implementeringar av multi-styrda CNOT-portar som bara kräver mycket få qubits och implementering av steg.</span><span class="sxs-lookup"><span data-stu-id="cc968-143">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>

<span data-ttu-id="cc968-144">I filen Canon finns exempel som använder nyckelordet `borrowing`, till exempel funktionen `MultiControlledXBorrow` som definieras nedan.</span><span class="sxs-lookup"><span data-stu-id="cc968-144">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="cc968-145">Om `controls` anger de kontroll-qubits som ska läggas till i en `X`-åtgärd, läggs en övergripande av `Length(controls)-2` många smutsig ancillas till av den här implementeringen.</span><span class="sxs-lookup"><span data-stu-id="cc968-145">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

<span data-ttu-id="cc968-146">Observera att den omfattande användningen av `With` Combinator----i formulär som är tillämplig för åtgärder som stöder intilliggande, d.v.s. `WithA`---har gjorts i det här exemplet, vilket är ett användbart programmerings format som att lägga till kontrollen till strukturer som inbegriper `With` bara sprider kontrollen till den inre åtgärden.</span><span class="sxs-lookup"><span data-stu-id="cc968-146">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example which is good programming style as adding control to structures involving `With` only propagates control to the inner operation.</span></span> <span data-ttu-id="cc968-147">Ytterligare information om detta utöver `body` av åtgärden är att en implementering av åtgärdens `controlled`s huvuddel uttryckligen tillhandahölls, i stället för att en `controlled auto`-instruktion används.</span><span class="sxs-lookup"><span data-stu-id="cc968-147">Further note that here in addition to the `body` of the operation an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span> <span data-ttu-id="cc968-148">Orsaken till detta är att vi vet från strukturen på kretsen som gör det enkelt att lägga till ytterligare kontroller som är fördelaktiga jämfört med att lägga till kontrollen till varje enskild grind i `body`.</span><span class="sxs-lookup"><span data-stu-id="cc968-148">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="cc968-149">Det är ett sätt att jämföra den här koden med en annan Canon Function-`MultiControlledXClean` som uppnår samma mål för att implementera en multiplicering-kontrollerad `X`-åtgärd, men som använder flera rena qubits med `using` mekanismen.</span><span class="sxs-lookup"><span data-stu-id="cc968-149">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 
