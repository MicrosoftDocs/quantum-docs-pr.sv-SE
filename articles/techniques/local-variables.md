---
title: 'Lokala variabler-Q #-tekniker'
description: 'Lär dig hur du definierar och arbetar med lokala variabler i Q #.'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: cb6c662137c31a13c3dd6e9ca3f67879c469f788
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906873"
---
# <a name="local-variables"></a><span data-ttu-id="4874b-103">Lokala variabler</span><span class="sxs-lookup"><span data-stu-id="4874b-103">Local Variables</span></span> #

<span data-ttu-id="4874b-104">Ett värde av valfri typ i Q # kan tilldelas en variabel för åter användning i en åtgärd eller funktion med hjälp av nyckelordet `let`.</span><span class="sxs-lookup"><span data-stu-id="4874b-104">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>
<span data-ttu-id="4874b-105">Exempel:</span><span class="sxs-lookup"><span data-stu-id="4874b-105">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="4874b-106">Detta tilldelar en viss matris av Pauli-operatörer till en variabel som kallas `measurementOperator`.</span><span class="sxs-lookup"><span data-stu-id="4874b-106">This assigns a particular array of Pauli operators to a variable called `measurementOperator`.</span></span>

> [!TIP]
> <span data-ttu-id="4874b-107">Observera att vi inte uttryckligen behöver ange typen av vår nya variabel, eftersom uttrycket till höger i instruktionen `let` är entydigt och att typen härleds av kompilatorn.</span><span class="sxs-lookup"><span data-stu-id="4874b-107">Note that we did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="4874b-108">Variabler i Q # är *oföränderliga*, vilket innebär att när en variabel har definierats på det här sättet kan den inte längre ändras på något sätt.</span><span class="sxs-lookup"><span data-stu-id="4874b-108">Variables in Q# are *immutable*, meaning that once a variable has been defined in this way, it can no longer be changed in any way.</span></span>
<span data-ttu-id="4874b-109">Detta möjliggör flera betalnings optimeringar, inklusive optimering av den klassiska logiken i variabler för att sorteras om för att tillämpa `Adjoint` varianten av en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="4874b-109">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

<span data-ttu-id="4874b-110">Variabler som definieras med `let` bindning som ovan är lokala i ett visst omfång, till exempel en åtgärds brödtext eller innehållet i en `for`-slinga.</span><span class="sxs-lookup"><span data-stu-id="4874b-110">Variables defined using the `let` binding as above are local to a particular scope, such as the body of an operation or the contents of a `for` loop.</span></span>


## <a name="mutability"></a><span data-ttu-id="4874b-111">Föränderlighet</span><span class="sxs-lookup"><span data-stu-id="4874b-111">Mutability</span></span> ##

<span data-ttu-id="4874b-112">Som ett alternativ till att skapa en variabel med `let`skapar nyckelordet `mutable` en speciell föränderligt-variabel som kan bindas igen efter att den ursprungligen har skapats med hjälp av nyckelordet `set`.</span><span class="sxs-lookup"><span data-stu-id="4874b-112">As an alternative to creating a variable with `let`, the `mutable` keyword will create a special mutable variable that can be re-bound after it is initially created by using the `set` keyword.</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

<span data-ttu-id="4874b-113">Alla typer i Q #, inklusive matriser, följer värde semantik.</span><span class="sxs-lookup"><span data-stu-id="4874b-113">All types in Q#, including arrays, follow value semantics.</span></span> <span data-ttu-id="4874b-114">I synnerhet är det inte möjligt att uppdatera mat ris objekt.</span><span class="sxs-lookup"><span data-stu-id="4874b-114">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="4874b-115">Om du vill ändra en befintlig matris måste du använda en kopierings-och-uppdatera-mekanism på samma F#sätt som för poster i.</span><span class="sxs-lookup"><span data-stu-id="4874b-115">To modify an existing array requires leveraging a copy-and-update mechanism much like the one for records in F#.</span></span> <span data-ttu-id="4874b-116">Med hjälp av biblioteks verktygen för matriser som finns i [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)kan vi enkelt definiera en funktion som returnerar en matris med Paul, där Pauli vid index `i` tar det givna värdet och alla andra poster är identiteten:</span><span class="sxs-lookup"><span data-stu-id="4874b-116">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can e.g. easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity:</span></span> 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

<span data-ttu-id="4874b-117">Vi kommer att utveckla mer om hur du arbetar med matriser när du diskuterar frågor och uttryck i Q #.</span><span class="sxs-lookup"><span data-stu-id="4874b-117">We will elaborate more on how to work with arrays when discussing Q# statements and expressions.</span></span> 

<span data-ttu-id="4874b-118">Föränderlighet inom Q # är ett koncept som gäller för en *symbol* i stället för en typ eller ett värde.</span><span class="sxs-lookup"><span data-stu-id="4874b-118">Mutability within Q# is a concept that applies to a *symbol* rather than a type or value.</span></span> <span data-ttu-id="4874b-119">Mer specifikt har det inte en representation i typ systemet, implicit eller explicit, och om en bindning är föränderligt (som anges av nyckelordet `mutable`) eller oföränderligt (som anges av `let`) inte ändrar typen för de variabla variabeln (erna).</span><span class="sxs-lookup"><span data-stu-id="4874b-119">Specifically, it does not have a representation in the type system, implicitly or explicitly, and whether or not a binding is mutable (as indicated by the `mutable` keyword) or immutable (as indicated by `let`) does not change the type of the bound variable(s).</span></span> <span data-ttu-id="4874b-120">Detta är ett viktigt sätt att isolera föränderlighet i specialiserade funktioner och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="4874b-120">This provides an important way to isolate mutability inside specialized functions and operations.</span></span>
<span data-ttu-id="4874b-121">I synnerhet, även om en angränsande specialisering för en åtgärd som använder en föränderligt-variabel inte kan genereras automatiskt, fungerar automatisk generering bra för en åtgärd som anropar en funktion som använder föränderlighet.</span><span class="sxs-lookup"><span data-stu-id="4874b-121">In particular, even though an adjoint specialization for an operation which uses a mutable variable cannot be auto-generated, auto-generation works fine for an operation calling a function which uses mutability.</span></span>
<span data-ttu-id="4874b-122">Av den anledningen är det en bra idé att skapa funktioner och åtgärder som använder föränderlighet som kort och komprimering som möjligt, så att resten av Quantum-programmet kan skrivas med vanliga variabler som inte kan ändras.</span><span class="sxs-lookup"><span data-stu-id="4874b-122">For this reason, it is a good practice to make functions and operations which use mutability as short and compact as possible, so that the rest of the quantum program can be written using ordinary immutable variables.</span></span>


## <a name="deconstruction"></a><span data-ttu-id="4874b-123">Avkonstruktion</span><span class="sxs-lookup"><span data-stu-id="4874b-123">Deconstruction</span></span> ##

<span data-ttu-id="4874b-124">Förutom att tilldela en enskild variabel, `let` och `mutable` nyckelord – eller i själva verket andra bindnings konstruktioner, så att du kan packa upp innehållet i en [tuple-typ](xref:microsoft.quantum.language.type-model#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="4874b-124">In addition to assigning a single variable, the `let` and `mutable` keywords - or in fact any other binding construct - also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.language.type-model#tuple-types).</span></span>
<span data-ttu-id="4874b-125">En tilldelning av det här formuläret är att *avkonstruera* elementen i denna tupel.</span><span class="sxs-lookup"><span data-stu-id="4874b-125">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>
<span data-ttu-id="4874b-126">Om vi till exempel modellerar en term i en Hamiltonian av en tupel, kan vi använda den för att få åtkomst till de olika data som vi behöver simulera under den perioden:</span><span class="sxs-lookup"><span data-stu-id="4874b-126">For instance, if we model a term in a Hamiltonian by a tuple, then we can use deconstruction to access the different data that we need to simulate under that term:</span></span>

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


