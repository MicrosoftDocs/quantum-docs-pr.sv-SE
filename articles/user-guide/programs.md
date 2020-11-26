---
title: 'Q # introdution'
description: 'Snabb introduktion till Quantum-program i Q #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234321"
---
# <a name="q-quantum-programming-language"></a><span data-ttu-id="99bda-103">Q # Quantum programmerings språk</span><span class="sxs-lookup"><span data-stu-id="99bda-103">Q# Quantum Programming Language</span></span>

<span data-ttu-id="99bda-104">Allt du behöver veta om programmeringsspråket Q # beskrivs i [språk guide för q #](xref:microsoft.quantum.qsharp.index).</span><span class="sxs-lookup"><span data-stu-id="99bda-104">Everything you need to know about the Q# programming language is detailed in the [Q# language guide](xref:microsoft.quantum.qsharp.index).</span></span> <span data-ttu-id="99bda-105">Precis som något annat är vår [språk design process](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) öppen källa och vi välkomnar bidrag.</span><span class="sxs-lookup"><span data-stu-id="99bda-105">Like anything else, our [language design process](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) is open source and we welcome contributions.</span></span>
<span data-ttu-id="99bda-106">Mer bakgrund om grunderna och motivation bakom Q # finns i [Varför behöver vi Q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span><span class="sxs-lookup"><span data-stu-id="99bda-106">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>  
<span data-ttu-id="99bda-107">Q # levereras som en del av Quantum Development Kit (QDK) för en snabb översikt, se [Vad är QDK?](xref:microsoft.quantum.overview.q-sharp).</span><span class="sxs-lookup"><span data-stu-id="99bda-107">Q# is shipped as part of the Quantum Development Kit (QDK) For a quick overview, check out [What is the QDK?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="99bda-108">Vad är ett Quantum-program?</span><span class="sxs-lookup"><span data-stu-id="99bda-108">What is a quantum program?</span></span>

<span data-ttu-id="99bda-109">Ett Quantum-program kan ses som en viss uppsättning klassiska under rutiner som, när de anropas, utför en beräkning genom att interagera med ett Quantum-system; ett program som är skrivet i Q # kan inte direkt modellera Quantum-tillstånd, utan beskriver i stället hur en klassisk kontroll dator interagerar med qubits.</span><span class="sxs-lookup"><span data-stu-id="99bda-109">A quantum program can be seen as a particular set of classical subroutines which, when called, perform a computation by interacting with a quantum system; a program written in Q# does not directly model the quantum state, but rather describes how a classical control computer interacts with qubits.</span></span>
<span data-ttu-id="99bda-110">På så sätt kan vi helt oberoende om vad ett Quantum-tillstånd *är* även på varje måldator, vilket kan ha olika tolkningar beroende på datorn.</span><span class="sxs-lookup"><span data-stu-id="99bda-110">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="99bda-111">En viktig följd av detta är att Q # inte har möjlighet att introspect till status för en qubit eller andra egenskaper för Quantum Mechanics direkt, vilket garanterar att ett Q #-program kan köras fysiskt på en dator med en Quantum-dator.</span><span class="sxs-lookup"><span data-stu-id="99bda-111">An important consequence of that is that Q# has no ability to introspect into the state of a qubit or other properties of quantum mechanics directly, which guarantees that a Q# program can be physically executed on a quantum computer.</span></span>
<span data-ttu-id="99bda-112">Ett program kan i stället anropa åtgärder, till exempel [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) för att extrahera klassisk information från en qubit.</span><span class="sxs-lookup"><span data-stu-id="99bda-112">Instead, a program can call operations such as [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) to extract classical information from a qubit.</span></span>

<span data-ttu-id="99bda-113">När den har allokerats kan en qubit skickas till åtgärder och funktioner, även kallat *callables*.</span><span class="sxs-lookup"><span data-stu-id="99bda-113">Once allocated, a qubit can be passed to operations and functions, also referred to as *callables*.</span></span> <span data-ttu-id="99bda-114">Detta är i viss bemärkelse att ett Q #-program kan göra med en qubit; Alla direkta åtgärder för status för en qubit definieras av en *inbyggd* callables, till exempel [`X`](xref:Microsoft.Quantum.Intrinsic.X) och [`H`](xref:Microsoft.Quantum.Intrinsic.H) -dvs. callables vars implementeringar inte har definierats inom Q # men definieras i stället av mål datorn.</span><span class="sxs-lookup"><span data-stu-id="99bda-114">In some sense, this is all that a Q# program can do with a qubit; Any direct actions on state of a qubit are all defined by *intrinsic* callables such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) - i.e. callables whose implementations are not defined within Q# but are instead defined by the target machine.</span></span> <span data-ttu-id="99bda-115">De här *åtgärderna faktiskt görs* enbart konkret av mål datorn som vi använder för att köra ett visst Q #-program.</span><span class="sxs-lookup"><span data-stu-id="99bda-115">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>

<span data-ttu-id="99bda-116">Om du till exempel kör programmet i en [full-State-Simulator](xref:microsoft.quantum.machines.full-state-simulator)utför simulatorn motsvarande matematiska åtgärder till det simulerade Quantum-systemet.</span><span class="sxs-lookup"><span data-stu-id="99bda-116">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="99bda-117">Men om mål datorn är en verklig Quantum-dator och du tittar på framtiden, så dirigerar de här åtgärderna i Q # den Quantum datorn för att utföra motsvarande *verkliga* åtgärder på det *verkliga* Quantum-systemet (t. ex. exakta tids bara laser pulser).</span><span class="sxs-lookup"><span data-stu-id="99bda-117">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="99bda-118">Ett Q #-program kombinerar dessa åtgärder så som definieras av en mål dator för att skapa nya, högre åtgärder för att uttrycka Quantum-beräkning.</span><span class="sxs-lookup"><span data-stu-id="99bda-118">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="99bda-119">På så sätt gör Q # det enkelt att uttrycka logiken för de underliggande Quantum-och hybrid Quantum-algoritmerna, samtidigt som det är allmänt vad gäller strukturen för en mål dator eller Simulator.</span><span class="sxs-lookup"><span data-stu-id="99bda-119">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

<span data-ttu-id="99bda-120">Ett enkelt exempel är följande program, som allokerar ett qubit i $ \ket {0} $-tillstånd, och sedan tillämpar en Hadamard-åtgärd `H` på den och mäter resultatet i `PauliZ` grunden.</span><span class="sxs-lookup"><span data-stu-id="99bda-120">A simple example is the following program, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

<span data-ttu-id="99bda-121">Vår [Quantum-Katas](https://github.com/microsoft/QuantumKatas#introduction) ger en bättre introduktion till [Quantum Computing-koncept](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) som vanliga Quantum-åtgärder och hur du manipulerar qubits.</span><span class="sxs-lookup"><span data-stu-id="99bda-121">Our [Quantum Katas](https://github.com/microsoft/QuantumKatas#introduction) give a good introduction on [Quantum Computing Concepts](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) such as common quantum operations and how to manipulate qubits.</span></span> <span data-ttu-id="99bda-122">Fler exempel finns även i [inbyggda funktioner och funktioner](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="99bda-122">More examples can also be found in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span>



