---
title: 'Skriv och simulera qubit-program i Q #'
description: Stegvisa anvisningar om hur du skriver och simulerar ett Quantum-program som fungerar på individuell qubit-nivå
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: f0b87936c9baf07555e76f295da58c0a6b9ecd17
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84328603"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a><span data-ttu-id="19305-103">Självstudie: Skriv och simulera qubit-program i Q\#</span><span class="sxs-lookup"><span data-stu-id="19305-103">Tutorial: Write and simulate qubit-level programs in Q\#</span></span>

<span data-ttu-id="19305-104">Välkommen till själv studie kursen om Quantum Development Kit om hur du skriver och simulerar ett grundläggande Quantum-program som fungerar på enskilda qubits.</span><span class="sxs-lookup"><span data-stu-id="19305-104">Welcome to the Quantum Development Kit tutorial on writing and simulating a basic quantum program that operates on individual qubits.</span></span> 

<span data-ttu-id="19305-105">Även om Q # ursprungligen skapades som ett högnivå-programmeringsspråk för storskaliga Quantum-program, kan det vara lika enkelt att använda för att utforska den lägre nivån av Quantum-program: direkt med specifika qubits.</span><span class="sxs-lookup"><span data-stu-id="19305-105">Although Q# was primarily created as a high-level programming language for large-scale quantum programs, it can just as easily be used to explore the lower level of quantum programs: directly addressing specific qubits.</span></span>
<span data-ttu-id="19305-106">Flexibiliteten i Q # gör det möjligt för användare att närma sig Quantum Systems från en sådan abstraktions nivå, och i den här självstudien får vi qubits själva.</span><span class="sxs-lookup"><span data-stu-id="19305-106">The flexibility of Q# allows users to approach quantum systems from any such level of abstraction, and in this tutorial we dive into the qubits themselves.</span></span>
<span data-ttu-id="19305-107">Mer specifikt tar vi en titt på den [Quantum Fourier-transformeringen](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), en subrutin som är integrerad med många större Quantum-algoritmer.</span><span class="sxs-lookup"><span data-stu-id="19305-107">Specifically, we take a look under the hood of the [quantum Fourier transform](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), a subroutine that is integral to many larger quantum algorithms.</span></span>

<span data-ttu-id="19305-108">Observera att den här lågnivå visningen av Quantum information Processing ofta beskrivs i termer av "[Quantum-kretsar](xref:microsoft.quantum.concepts.circuits)", som representerar sekventiell användning av portar till specifika qubits i ett system.</span><span class="sxs-lookup"><span data-stu-id="19305-108">Note that this low-level view of quantum information processing is often described in terms of "[quantum circuits](xref:microsoft.quantum.concepts.circuits)," which represent the sequential application of gates to specific qubits of a system.</span></span>

<span data-ttu-id="19305-109">Det innebär att en och flera qubit-åtgärder som vi tillämpar sekventiellt kan visas i ett "krets diagram".</span><span class="sxs-lookup"><span data-stu-id="19305-109">Thus, the single- and multi-qubit operations we sequentially apply can be readily represented in a "circuit diagram."</span></span>
<span data-ttu-id="19305-110">I vårt fall definierar vi en Q #-åtgärd för att utföra en fullständig qubit Quantum Fourier-transformering, som har följande åter givning som krets:</span><span class="sxs-lookup"><span data-stu-id="19305-110">In our case, we will define a Q# operation to perform the full three-qubit quantum Fourier transform, which has the following representation as a circuit:</span></span>

<br/>
<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a><span data-ttu-id="19305-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="19305-111">Prerequisites</span></span>

* <span data-ttu-id="19305-112">[Installera](xref:microsoft.quantum.install) Quantum Development Kit med din önskade språk-och utvecklings miljö.</span><span class="sxs-lookup"><span data-stu-id="19305-112">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment.</span></span>
* <span data-ttu-id="19305-113">Om du redan har installerat QDK kontrollerar du att det är [uppdaterat](xref:microsoft.quantum.update) till den senaste versionen</span><span class="sxs-lookup"><span data-stu-id="19305-113">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>


## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="19305-114">I den här självstudien får du lära dig att:</span><span class="sxs-lookup"><span data-stu-id="19305-114">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="19305-115">Definiera Quantum-åtgärder i Q #</span><span class="sxs-lookup"><span data-stu-id="19305-115">Define quantum operations in Q#</span></span>
> * <span data-ttu-id="19305-116">Anropa Q #-åtgärder direkt från kommando raden eller med hjälp av ett klassiskt värd program</span><span class="sxs-lookup"><span data-stu-id="19305-116">Call Q# operations directly from the command line or using a classical host program</span></span>
> * <span data-ttu-id="19305-117">Simulera en Quantum-åtgärd från qubit-allokering till mått utdata</span><span class="sxs-lookup"><span data-stu-id="19305-117">Simulate a quantum operation from qubit allocation to measurement output</span></span>
> * <span data-ttu-id="19305-118">Observera hur Quantum Systems simulerade wavefunction utvecklas under hela åtgärden</span><span class="sxs-lookup"><span data-stu-id="19305-118">Observe how the quantum system's simulated wavefunction evolves throughout the operation</span></span>

<span data-ttu-id="19305-119">Att köra ett Quantum-program med Microsofts Quantum Development Kit består vanligt vis av två delar:</span><span class="sxs-lookup"><span data-stu-id="19305-119">Running a quantum program with Microsoft's Quantum Development Kit typically consists of two parts:</span></span>
1. <span data-ttu-id="19305-120">Själva programmet, som implementeras med hjälp av programmeringsspråket Q # Quantum, och sedan anropas för körning på en Quantum-dator eller Quantum-Simulator.</span><span class="sxs-lookup"><span data-stu-id="19305-120">The program itself, which is implemented using the Q# quantum programming language, and then invoked to run on a quantum computer or quantum simulator.</span></span> <span data-ttu-id="19305-121">Detta består av</span><span class="sxs-lookup"><span data-stu-id="19305-121">These consist of</span></span> 
    - <span data-ttu-id="19305-122">Q #-åtgärder: under rutiner som fungerar på Quantum-register och</span><span class="sxs-lookup"><span data-stu-id="19305-122">Q# operations: subroutines acting on quantum registers, and</span></span> 
    - <span data-ttu-id="19305-123">Q # functions: klassiska under rutiner som används inom Quantum-algoritmen.</span><span class="sxs-lookup"><span data-stu-id="19305-123">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="19305-124">Start punkten som används för att anropa programmet Quantum och ange den måldator som den ska köras på.</span><span class="sxs-lookup"><span data-stu-id="19305-124">The entry point used to call the quantum program and specify the target machine on which it should be run.</span></span>
    <span data-ttu-id="19305-125">Detta kan göras direkt från kommando raden eller via ett värd program som skrivits i ett klassiskt programmeringsspråk som python eller C#.</span><span class="sxs-lookup"><span data-stu-id="19305-125">This can be done directly from the command line, or through a host program written in a classical programming language like Python or C#.</span></span>
    <span data-ttu-id="19305-126">Den här självstudien innehåller instruktioner för vilken metod du föredrar.</span><span class="sxs-lookup"><span data-stu-id="19305-126">This tutorial includes instructions for whichever method you prefer.</span></span>

## <a name="allocate-qubits-and-define-quantum-operations"></a><span data-ttu-id="19305-127">Allokera qubits och definiera Quantum-åtgärder</span><span class="sxs-lookup"><span data-stu-id="19305-127">Allocate qubits and define quantum operations</span></span>

<span data-ttu-id="19305-128">Den första delen av den här självstudien består av att definiera Q # `Perform3qubitQFT` -åtgärden, som utför Fourier-transformeringen på tre qubits.</span><span class="sxs-lookup"><span data-stu-id="19305-128">The first part of this tutorial consists of defining the Q# operation `Perform3qubitQFT`, which performs the quantum Fourier transform on three qubits.</span></span> 

<span data-ttu-id="19305-129">Dessutom kommer vi [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) att använda funktionen för att se hur den simulerade wavefunction av vårt tre qubit-system utvecklas över hela åtgärden.</span><span class="sxs-lookup"><span data-stu-id="19305-129">In addition, we will use the [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) function to observe how the simulated wavefunction of our three qubit system evolves across the operation.</span></span>

<span data-ttu-id="19305-130">Det första steget är att skapa ditt Q #-projekt och-fil.</span><span class="sxs-lookup"><span data-stu-id="19305-130">The first step is creating your Q# project and file.</span></span>
<span data-ttu-id="19305-131">Stegen för detta beror på vilken miljö du ska använda för att anropa programmet, och du hittar informationen i respektive [installations guide](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="19305-131">The steps for this depend on the environment you will use to call the program, and you can find the details in the respective [installation guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="19305-132">Vi vägleder dig genom komponenterna i filen Step-by-Step, men koden är även tillgänglig som ett fullständigt block nedan.</span><span class="sxs-lookup"><span data-stu-id="19305-132">We will walk you through the components of the file step-by-step, but the code is also available as a full block below.</span></span>

### <a name="namespaces-to-access-other-q-operations"></a><span data-ttu-id="19305-133">Namn områden för att få åtkomst till andra Q #-åtgärder</span><span class="sxs-lookup"><span data-stu-id="19305-133">Namespaces to access other Q# operations</span></span>
<span data-ttu-id="19305-134">Inuti filen definierar vi först namn området `NamespaceQFT` som ska användas av kompileraren.</span><span class="sxs-lookup"><span data-stu-id="19305-134">Inside the file, we first define the namespace `NamespaceQFT` which will be accessed by the compiler.</span></span>
<span data-ttu-id="19305-135">För att vår åtgärd ska kunna använda befintliga Q #-åtgärder öppnar vi relevanta `Microsoft.Quantum.<>` namn områden.</span><span class="sxs-lookup"><span data-stu-id="19305-135">For our operation to make use of existing Q# operations, we open the relevant `Microsoft.Quantum.<>` namespaces.</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a><span data-ttu-id="19305-136">Definiera åtgärder med argument och returer</span><span class="sxs-lookup"><span data-stu-id="19305-136">Define operations with arguments and returns</span></span>
<span data-ttu-id="19305-137">Nu definierar vi `Perform3qubitQFT` åtgärden:</span><span class="sxs-lookup"><span data-stu-id="19305-137">Next, we define the `Perform3qubitQFT` operation:</span></span>

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

<span data-ttu-id="19305-138">För tillfället tar åtgärden inga argument och returnerar inte något---i det här fallet skriver vi att den returnerar ett `Unit` objekt, som är via till `void` i C# eller en tom tupel, `Tuple[()]` i python.</span><span class="sxs-lookup"><span data-stu-id="19305-138">For now, the operation takes no arguments and does not return anything---in this case we write that it returns a `Unit` object, which is akin to `void` in C# or an empty tuple, `Tuple[()]`, in Python.</span></span>
<span data-ttu-id="19305-139">Senare kommer vi att ändra den så att den returnerar en matris med mät resultat, då `Unit` ersätts punkten med `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="19305-139">Later, we will modify it to return an array of measurement results, at which point `Unit` will be replaced by `Result[]`.</span></span> 

### <a name="allocate-qubits-with-using"></a><span data-ttu-id="19305-140">Allokera qubits med`using`</span><span class="sxs-lookup"><span data-stu-id="19305-140">Allocate qubits with `using`</span></span>
<span data-ttu-id="19305-141">Inom vår Q #-åtgärd allokerar vi först ett register över tre qubits med `using` instruktionen:</span><span class="sxs-lookup"><span data-stu-id="19305-141">Within our Q# operation, we first allocate a register of three qubits with the `using` statement:</span></span>

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

<span data-ttu-id="19305-142">Med `using` tilldelas qubits automatiskt i $ \ket {0} $-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="19305-142">With `using`, the qubits are automatically allocated in the $\ket{0}$ state.</span></span> <span data-ttu-id="19305-143">Vi kan verifiera detta genom att använda [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) och [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , som skriver ut en sträng och systemets aktuella tillstånd till-konsolen.</span><span class="sxs-lookup"><span data-stu-id="19305-143">We can verify this by using [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) and [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine), which print a string and the system's current state to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="19305-144">`Message(<string>)`-Och- `DumpMachine()` funktionerna ( [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) både från och [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) respektive) skrivs direkt till-konsolen.</span><span class="sxs-lookup"><span data-stu-id="19305-144">The `Message(<string>)` and `DumpMachine()` functions (from [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics), respectively) both print directly to the console.</span></span> <span data-ttu-id="19305-145">Precis som en verklig Quantum-beräkning tillåter inte Q # att vi direkt kommer åt qubit-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="19305-145">Just like a real quantum computation, Q# does not allow us to directly access qubit states.</span></span>
> <span data-ttu-id="19305-146">I takt `DumpMachine` med att mål datorns aktuella tillstånd skrivs ut, kan det dock ge värdefull information om fel sökning och inlärning när det används tillsammans med fullständig tillstånds Simulator.</span><span class="sxs-lookup"><span data-stu-id="19305-146">However, as `DumpMachine` prints the target machine's current state, it can provide valuable insight for debugging and learning when used in conjunction with the full state simulator.</span></span>


### <a name="applying-single-qubit-and-controlled-gates"></a><span data-ttu-id="19305-147">Använda en qubit och kontrollerade portar</span><span class="sxs-lookup"><span data-stu-id="19305-147">Applying single-qubit and controlled gates</span></span>

<span data-ttu-id="19305-148">Därefter tillämpar vi de portar som utgör själva åtgärden.</span><span class="sxs-lookup"><span data-stu-id="19305-148">Next, we apply the gates which comprise the operation itself.</span></span>
<span data-ttu-id="19305-149">Q # innehåller redan många grundläggande Quantum-grindar som åtgärder i [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) namn området och dessa är inget undantag.</span><span class="sxs-lookup"><span data-stu-id="19305-149">Q# already contains many basic quantum gates as operations in the [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) namespace, and these are no exception.</span></span> 

<span data-ttu-id="19305-150">Inom en Q #-åtgärd körs de instruktioner som anropar callables i turordning.</span><span class="sxs-lookup"><span data-stu-id="19305-150">Within a Q# operation, the statements invoking callables will of course be executed in sequential order.</span></span>
<span data-ttu-id="19305-151">Den första porten som ska tillämpas är därför [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) för den första qubit:</span><span class="sxs-lookup"><span data-stu-id="19305-151">Hence, the first gate to apply is the [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) to the first qubit:</span></span>

<br/>
<img src="./qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

<span data-ttu-id="19305-152">Om du vill tillämpa en åtgärd på en viss qubit från ett register (d.v.s. en enskild `Qubit` från en matris `Qubit[]` ) använder vi standard index notation.</span><span class="sxs-lookup"><span data-stu-id="19305-152">To apply an operation to a specific qubit from a register (i.e. a single `Qubit` from an array `Qubit[]`) we use standard index notation.</span></span>
<span data-ttu-id="19305-153">Det gör att du kan använda den [`H`](xref:microsoft.quantum.intrinsic.h) första qubit i vårt register för att göra `qs` formuläret:</span><span class="sxs-lookup"><span data-stu-id="19305-153">So, applying the [`H`](xref:microsoft.quantum.intrinsic.h) to the first qubit of our register `qs` takes the form:</span></span>

```qsharp
            H(qs[0]);
```

<span data-ttu-id="19305-154">Förutom att tillämpa `H` Hadamard-porten på enskilda qubits, består QFT-kretsen främst av kontrollerade [`R1`](xref:microsoft.quantum.intrinsic.r1) rotationer.</span><span class="sxs-lookup"><span data-stu-id="19305-154">Besides applying the `H` (Hadamard) gate to individual qubits, the QFT circuit consists primarily of controlled [`R1`](xref:microsoft.quantum.intrinsic.r1) rotations.</span></span>
<span data-ttu-id="19305-155">En `R1(θ, <qubit>)` åtgärd i allmänhet lämnar $ \ket {0} $-komponenten i qubit oförändrad och använder en rotation av $e ^ {i\theta} $ till $ \ket {1} $-komponenten.</span><span class="sxs-lookup"><span data-stu-id="19305-155">An `R1(θ, <qubit>)` operation in general leaves the $\ket{0}$ component of the qubit unchanged, while applying a rotation of $e^{i\theta}$ to the $\ket{1}$ component.</span></span>

#### <a name="controlled-operations"></a><span data-ttu-id="19305-156">Kontrollerade åtgärder</span><span class="sxs-lookup"><span data-stu-id="19305-156">Controlled operations</span></span>

<span data-ttu-id="19305-157">Q # gör det mycket enkelt att utvärdera körningen av en åtgärd på en eller flera qubits.</span><span class="sxs-lookup"><span data-stu-id="19305-157">Q# makes it extremely easy to condition the execution of an operation upon one or multiple control qubits.</span></span>
<span data-ttu-id="19305-158">I allmänhet inleder vi bara anropet med `Controlled` och åtgärds argumenten ändras som:</span><span class="sxs-lookup"><span data-stu-id="19305-158">In general, we merely preface the call with `Controlled`, and the operation arguments change as:</span></span>

 <span data-ttu-id="19305-159">`Op(<normal args>)`$ \to $ `Controlled Op([<control qubits>], (<normal args>))` .</span><span class="sxs-lookup"><span data-stu-id="19305-159">`Op(<normal args>)` $\to$ `Controlled Op([<control qubits>], (<normal args>))`.</span></span>

<span data-ttu-id="19305-160">Observera att kontrollen qubits måste anges som en matris, även om det är en enskild qubit.</span><span class="sxs-lookup"><span data-stu-id="19305-160">Note that the control qubits must be provided as an array, even if it is a single qubit.</span></span>

<span data-ttu-id="19305-161">Efter det `H` ser vi att nästa grind är de portar som `R1` agerar på den första qubit (och styrs av den andra/tredje):</span><span class="sxs-lookup"><span data-stu-id="19305-161">After the `H`, we see that the next gates are the `R1` gates acting on the first qubit (and controlled by the second/third):</span></span>

<br/>
<img src="./qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

<span data-ttu-id="19305-162">Vi kallar dessa med</span><span class="sxs-lookup"><span data-stu-id="19305-162">We call these with</span></span>

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

<span data-ttu-id="19305-163">Observera att vi använder [`PI()`](xref:microsoft.quantum.math.pi) funktionen från [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namn området för att definiera rotationen i form av pi radianer.</span><span class="sxs-lookup"><span data-stu-id="19305-163">Note that we use the [`PI()`](xref:microsoft.quantum.math.pi) function from the [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namespace to define the rotations in terms of pi radians.</span></span>
<span data-ttu-id="19305-164">Dessutom delas vi upp av en `Double` (t. ex. `2.0` ) eftersom division av ett heltal `2` skulle resultera i ett typ fel.</span><span class="sxs-lookup"><span data-stu-id="19305-164">Additionally, we divide by a `Double` (e.g. `2.0`) because dividing by an integer `2` would throw a type error.</span></span> 

> [!TIP]
> <span data-ttu-id="19305-165">`R1(π/2)`och `R1(π/4)` motsvarar `S` `T` -och-åtgärderna (även i `Microsoft.Quantum.Intrinsic` ).</span><span class="sxs-lookup"><span data-stu-id="19305-165">`R1(π/2)` and `R1(π/4)` are equivalent to the `S` and `T` operations (also in `Microsoft.Quantum.Intrinsic`).</span></span>


<span data-ttu-id="19305-166">Efter att ha tillämpat relevanta `H` åtgärder och kontrollerade rotationer för den andra och tredje qubits:</span><span class="sxs-lookup"><span data-stu-id="19305-166">After applying the relevant `H` operations and controlled rotations to the second and third qubits:</span></span>

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

<span data-ttu-id="19305-167">Vi behöver bara tillämpa en [`SWAP`](xref:microsoft.quantum.intrinsic.swap) grind för att slutföra kretsen:</span><span class="sxs-lookup"><span data-stu-id="19305-167">we need only apply a [`SWAP`](xref:microsoft.quantum.intrinsic.swap) gate to complete the circuit:</span></span>

```qsharp
            SWAP(qs[2], qs[0]);
```

<span data-ttu-id="19305-168">Detta är nödvändigt eftersom typen av Fourier-transformeringen matar ut qubits i omvänd ordning, så att växlingarna tillåter sömlös integrering av underrutinen i större algoritmer.</span><span class="sxs-lookup"><span data-stu-id="19305-168">This is necessary because the nature of the quantum Fourier transform outputs the qubits in reverse order, so the swaps allow for seamless integration of the subroutine into larger algorithms.</span></span>

<span data-ttu-id="19305-169">Vi har därför skrivit klart qubit-åtgärderna för Quantum Fourier-transformeringen i vår Q #-åtgärd:</span><span class="sxs-lookup"><span data-stu-id="19305-169">Hence we have finished writing the qubit-level operations of the quantum Fourier transform into our Q# operation:</span></span>

<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

<span data-ttu-id="19305-170">Vi kan dock inte anropa den en dag ännu.</span><span class="sxs-lookup"><span data-stu-id="19305-170">However, we can't call it a day just yet.</span></span>
<span data-ttu-id="19305-171">Vår qubits har status $ \ket {0} $ när vi allokerade dem, och ungefär som i livet, i Q # bör vi lämna saker på samma sätt som vi hittade dem (eller bättre!).</span><span class="sxs-lookup"><span data-stu-id="19305-171">Our qubits were in state $\ket{0}$ when we allocated them, and much like in life, in Q# we should leave things the same way we found them (or better!).</span></span>

### <a name="deallocate-qubits"></a><span data-ttu-id="19305-172">Frigör qubits</span><span class="sxs-lookup"><span data-stu-id="19305-172">Deallocate qubits</span></span>

<span data-ttu-id="19305-173">Vi anropar [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) igen för att se status efter åtgärden och slutligen använder du [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) qubit-registret för att återställa vår qubits till $ \ket {0} $ innan du Slutför åtgärden:</span><span class="sxs-lookup"><span data-stu-id="19305-173">We call [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) again to see the post-operation state, and finally apply [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) to the qubit register to reset our qubits to $\ket{0}$ before completing the operation:</span></span>

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

<span data-ttu-id="19305-174">Att kräva att alla avallokerade qubits uttryckligen anges till $ \ket {0} $ är en grundläggande funktion i Q #, eftersom det gör det möjligt för andra åtgärder att identifiera sitt tillstånd exakt när de börjar använda samma qubits (en begränsade-resurs).</span><span class="sxs-lookup"><span data-stu-id="19305-174">Requiring that all deallocated qubits be explicitly set to $\ket{0}$ is a basic feature of Q#, as it allows other operations to know their state precisely when they begin using those same qubits (a scarce resource).</span></span>
<span data-ttu-id="19305-175">Detta säkerställer också att de inte är Entangled med andra qubits i systemet.</span><span class="sxs-lookup"><span data-stu-id="19305-175">Additionally, this assures that they not be entangled with any other qubits in the system.</span></span>
<span data-ttu-id="19305-176">Om återställningen inte utförs i slutet av ett `using` tilldelnings block kommer ett körnings fel att genereras.</span><span class="sxs-lookup"><span data-stu-id="19305-176">If the reset is not performed at the end of a `using` allocation block, a runtime error will be thrown.</span></span>

<span data-ttu-id="19305-177">Den fullständiga Q #-filen bör nu se ut så här:</span><span class="sxs-lookup"><span data-stu-id="19305-177">Your full Q# file should now look like this:</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


<span data-ttu-id="19305-178">När Q #-filen och åtgärden har slutförts är vårt Quantum-program klart att anropas och simuleras.</span><span class="sxs-lookup"><span data-stu-id="19305-178">With the Q# file and operation complete, our quantum program is ready to be called and simulated.</span></span>

## <a name="execute-the-program"></a><span data-ttu-id="19305-179">Kör programmet</span><span class="sxs-lookup"><span data-stu-id="19305-179">Execute the program</span></span>

<span data-ttu-id="19305-180">När vi har definierat vår Q #-åtgärd i en `.qs` fil måste vi nu anropa den åtgärden och observera eventuella data som returneras.</span><span class="sxs-lookup"><span data-stu-id="19305-180">Having defined our Q# operation in a `.qs` file, we now need to call that operation and observe any returned classical data.</span></span>
<span data-ttu-id="19305-181">För tillfället finns det inga returnerade (kom ihåg att vår åtgärd som definierats ovan returnerar `Unit` ), men när vi senare ändrar Q #-åtgärden för att returnera en matris med mått resultat ( `Result[]` ), kommer vi att adressera detta.</span><span class="sxs-lookup"><span data-stu-id="19305-181">For now, there isn't anything returned (recall that our operation defined above returns `Unit`), but when we later modify the Q# operation to return an array of measurement results (`Result[]`), we will address this.</span></span>

<span data-ttu-id="19305-182">Medan Q #-programmet är allmänt förekommandet i de miljöer som används för att anropa det, kan det vara självklart att göra det.</span><span class="sxs-lookup"><span data-stu-id="19305-182">While the Q# program is ubiquitous across the environments used to call it, the manner of doing so will of course vary.</span></span> <span data-ttu-id="19305-183">Det gör du genom att följa anvisningarna i den flik som motsvarar konfigurationen: arbeta från kommando rads programmet för Q # eller använda ett värd program i python eller C#.</span><span class="sxs-lookup"><span data-stu-id="19305-183">As such, simply follow the instructions in the tab corresponding to your setup: working from the Q# command line application or using a host program in Python or C#.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="19305-184">Kommandorad</span><span class="sxs-lookup"><span data-stu-id="19305-184">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="19305-185">Att köra Q #-programmet från kommando raden kräver bara en liten ändring i Q #-filen.</span><span class="sxs-lookup"><span data-stu-id="19305-185">Running the Q# program from the command line requires only a small change to the Q# file.</span></span>

<span data-ttu-id="19305-186">Lägg bara till `@EntryPoint()` på en rad före åtgärds definitionen:</span><span class="sxs-lookup"><span data-stu-id="19305-186">Simply add `@EntryPoint()` to a line preceding the operation definition:</span></span>

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

<span data-ttu-id="19305-187">Om du vill köra programmet öppnar du terminalen i mappen i projektet och anger</span><span class="sxs-lookup"><span data-stu-id="19305-187">To run the program, open the terminal in the folder of your project and enter</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="19305-188">Vid körningen bör du se `Message` och `DumpMachine` utmatningarna nedan som skrivs ut i konsolen.</span><span class="sxs-lookup"><span data-stu-id="19305-188">Upon execution, you should see the `Message` and `DumpMachine` outputs below printed in your console.</span></span>


#### <a name="python"></a>[<span data-ttu-id="19305-189">Python</span><span class="sxs-lookup"><span data-stu-id="19305-189">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="19305-190">Skapa en python-värd fil: `host.py` .</span><span class="sxs-lookup"><span data-stu-id="19305-190">Create a Python host file: `host.py`.</span></span>

<span data-ttu-id="19305-191">Värd filen skapas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="19305-191">The host file is constructed as follows:</span></span> 
1. <span data-ttu-id="19305-192">Först importerar vi `qsharp` modulen som registrerar modulens inläsare för Q #-samverkan.</span><span class="sxs-lookup"><span data-stu-id="19305-192">First, we import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="19305-193">Detta gör att Q #-namnområden (t. ex. `NamespaceQFT` vi definierat i vår Q #-fil) visas som python-moduler, där vi kan importera Q #-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="19305-193">This allows Q# namespaces (e.g. the `NamespaceQFT` we defined in our Q# file) to appear as Python modules, from which we can import Q# operations.</span></span>
2. <span data-ttu-id="19305-194">Importera sedan de Q #-åtgärder som vi kommer att anropa direkt---i det här fallet `Perform3qubitQFT` .</span><span class="sxs-lookup"><span data-stu-id="19305-194">Then, import the Q# operations which we will directly invoke---in this case, `Perform3qubitQFT`.</span></span>
    <span data-ttu-id="19305-195">Vi behöver bara importera start punkten till ett Q #-program (d.v.s. _inte_ åtgärder som `H` och `R1` , som anropas av andra Q #-åtgärder men aldrig av den klassiska värden).</span><span class="sxs-lookup"><span data-stu-id="19305-195">We need only import the entry point into a Q# program (i.e. _not_ operations like `H` and `R1`, which are called by other Q# operations but never by the classical host).</span></span>
3. <span data-ttu-id="19305-196">I simulera Q #-åtgärder eller-funktioner använder du formuläret `<Q#callable>.simulate(<args>)` för att köra dem på `QuantumSimulator()` mål datorn.</span><span class="sxs-lookup"><span data-stu-id="19305-196">In simulating Q# operations or functions, use the form `<Q#callable>.simulate(<args>)` to run them on the `QuantumSimulator()` target machine.</span></span> 

> [!NOTE]
> <span data-ttu-id="19305-197">Om vi ville anropa åtgärden på en annan dator, till exempel `ResourceEstimator()` , skulle vi bara använda `<Q#callable>.estimate_resources(<args>)` .</span><span class="sxs-lookup"><span data-stu-id="19305-197">If we wanted to call the operation on a different machine, for example the `ResourceEstimator()`, we would simply use `<Q#callable>.estimate_resources(<args>)`.</span></span>
> <span data-ttu-id="19305-198">I allmänhet är Q #-åtgärder oberoende till de datorer där de körs, men vissa funktioner som `DumpMachine` kan fungera annorlunda.</span><span class="sxs-lookup"><span data-stu-id="19305-198">In general, Q# operations are agnostic to the machines on which they're run, but some features such as `DumpMachine` may behave differently.</span></span>

4. <span data-ttu-id="19305-199">När du utför simuleringen returnerar åtgärds anropet värden som definieras i Q #-filen.</span><span class="sxs-lookup"><span data-stu-id="19305-199">Upon performing the simulation, the operation call will return values as defined in the Q# file.</span></span>
    <span data-ttu-id="19305-200">För tillfället finns inga returnerade, men senare visas ett exempel på att tilldela och bearbeta dessa värden.</span><span class="sxs-lookup"><span data-stu-id="19305-200">For now there is nothing returned, but later on we will see an example of assigning and processing these values.</span></span>
    <span data-ttu-id="19305-201">Med resultat data i våra händer och helt klassiska kan vi göra vad vi vill med det.</span><span class="sxs-lookup"><span data-stu-id="19305-201">With the resultant data in our hands and totally classical, we can do whatever we'd like with it.</span></span>

<span data-ttu-id="19305-202">Den fullständiga `host.py` filen bör vara följande:</span><span class="sxs-lookup"><span data-stu-id="19305-202">Your full `host.py` file should be this:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

<span data-ttu-id="19305-203">Kör python-filen och skriv ut i konsolen. du bör se `Message` och `DumpMachine` utdata nedan.</span><span class="sxs-lookup"><span data-stu-id="19305-203">Run the Python file, and printed in your console you should see the `Message` and `DumpMachine` outputs below.</span></span> 


#### <a name="c"></a>[<span data-ttu-id="19305-204">C#</span><span class="sxs-lookup"><span data-stu-id="19305-204">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="19305-205">Följ samma instruktioner som i [installations guiden](xref:microsoft.quantum.install.cs), skapa en C#-värd fil och Byt namn på den till `host.cs` .</span><span class="sxs-lookup"><span data-stu-id="19305-205">Following the same instructions as in the [install guide](xref:microsoft.quantum.install.cs), create a C# host file, and rename it to `host.cs`.</span></span>

<span data-ttu-id="19305-206">C#-värden består av fyra delar:</span><span class="sxs-lookup"><span data-stu-id="19305-206">The C# host has four parts:</span></span>
1. <span data-ttu-id="19305-207">Konstruera en kvantsimulator.</span><span class="sxs-lookup"><span data-stu-id="19305-207">Construct a quantum simulator.</span></span>
    <span data-ttu-id="19305-208">I koden nedan är detta variabeln `qsim` .</span><span class="sxs-lookup"><span data-stu-id="19305-208">In the code below, this is the variable `qsim`.</span></span>
2. <span data-ttu-id="19305-209">Beräkna eventuella argument som krävs för kvantalgoritmen.</span><span class="sxs-lookup"><span data-stu-id="19305-209">Compute any arguments required for the quantum algorithm.</span></span>
    <span data-ttu-id="19305-210">Det finns inga i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="19305-210">There are none in this example.</span></span>
3. <span data-ttu-id="19305-211">Köra kvantalgoritmen.</span><span class="sxs-lookup"><span data-stu-id="19305-211">Run the quantum algorithm.</span></span> 
    <span data-ttu-id="19305-212">Varje Q#-åtgärd genererar en C#-klass med samma namn.</span><span class="sxs-lookup"><span data-stu-id="19305-212">Each Q# operation generates a C# class with the same name.</span></span> 
    <span data-ttu-id="19305-213">Den här klassen innehåller en `Run`-metod som **asynkront** utför åtgärden.</span><span class="sxs-lookup"><span data-stu-id="19305-213">This class has a `Run` method that **asynchronously** executes the operation.</span></span>
    <span data-ttu-id="19305-214">Körningen är asynkron eftersom körningen på den faktiska maskinvaran kommer att vara asynkron.</span><span class="sxs-lookup"><span data-stu-id="19305-214">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> 
    <span data-ttu-id="19305-215">Eftersom `Run` metoden är asynkron anropar vi `Wait()` metoden. Detta blockerar körningen tills aktiviteten har slutförts och returnerar resultatet synkront.</span><span class="sxs-lookup"><span data-stu-id="19305-215">Because the `Run` method is asynchronous, we call the `Wait()` method; this blocks execution until the task completes and returns the result synchronously.</span></span> 
4. <span data-ttu-id="19305-216">Bearbeta det returnerade resultatet för åtgärden.</span><span class="sxs-lookup"><span data-stu-id="19305-216">Process the returned result of the operation.</span></span>
    <span data-ttu-id="19305-217">För tillfället returnerar åtgärden ingenting.</span><span class="sxs-lookup"><span data-stu-id="19305-217">For now, the operation returns nothing.</span></span>


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
<span data-ttu-id="19305-218">Kör programmet och dina utdata bör överensstämma nedan.</span><span class="sxs-lookup"><span data-stu-id="19305-218">Run the application, and your output should match that below.</span></span>
<span data-ttu-id="19305-219">Programmet avslutas när du har tryckt på en tangent.</span><span class="sxs-lookup"><span data-stu-id="19305-219">The program will exit after you press a key.</span></span>
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

<span data-ttu-id="19305-220">När den anropas i full-State Simulator `DumpMachine()` tillhandahåller dessa flera-representationer av Quantum States wavefunction.</span><span class="sxs-lookup"><span data-stu-id="19305-220">When called on the full-state simulator, `DumpMachine()` provides these mutliple representations of the quantum state's wavefunction.</span></span> <span data-ttu-id="19305-221">Möjliga tillstånd för ett $n $-qubit-system kan representeras av $2 ^ n $ beräknings bas tillstånd, var och en med en motsvarande komplex koefficient (helt enkelt en amplitud och en fas).</span><span class="sxs-lookup"><span data-stu-id="19305-221">The possible states of an $n$-qubit system can be represented by $2^n$ computational basis states, each with a corresponding complex coefficient (simply an amplitude and a phase).</span></span>
<span data-ttu-id="19305-222">Beräknings bas staterna motsvarar alla möjliga binära strängar $n $---det vill säga alla möjliga kombinationer av qubit-tillstånd $ \ket {0} $ och $ \ket {1} $, där varje binär siffra motsvarar en enskild qubit.</span><span class="sxs-lookup"><span data-stu-id="19305-222">The computational basis states correspond to all the possible binary strings of length $n$---that is, all the possible combinations of qubit states $\ket{0}$ and $\ket{1}$, where each binary digit corresponds to an individual qubit.</span></span>

<span data-ttu-id="19305-223">Den första raden innehåller en kommentar med ID: n för motsvarande qubits i sin betydande ordning.</span><span class="sxs-lookup"><span data-stu-id="19305-223">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="19305-224">Qubit `2` är "mest betydelsefull" innebär bara att i den binära representationen av bas tillstånds vektor $ \ket{i} $, motsvarar status för qubit `2` värdet längst till vänster.</span><span class="sxs-lookup"><span data-stu-id="19305-224">Qubit `2` being the "most significant" simply means that in the binary representation of basis state vector $\ket{i}$, the state of qubit `2` corresponds to the left-most digit.</span></span> <span data-ttu-id="19305-225">Till exempel $ \ket {6} = \ket {110} $ omfattar qubits `2` och `1` både i $ \ket {1} $ och qubit `0` i $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="19305-225">For example, $\ket{6} = \ket{110}$ comprises qubits `2` and `1` both in $\ket{1}$ and qubit `0` in $\ket{0}$.</span></span>


<span data-ttu-id="19305-226">Resten av raderna beskriver sannolikheten för att mäta bas läget Vector $ \ket{i} $ i båda formaten kartesiska och Polar.</span><span class="sxs-lookup"><span data-stu-id="19305-226">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{i}$ in both Cartesian and polar formats.</span></span>
<span data-ttu-id="19305-227">I detalj för den första raden i vårt indatamängds tillstånd $ \ket {000} $:</span><span class="sxs-lookup"><span data-stu-id="19305-227">In detail for the first row of our input state $\ket{000}$:</span></span>
* <span data-ttu-id="19305-228">**`|0>:`** den här raden motsvarar `0` beräknings bas läget (eftersom vår initiala status efter allokering var $ \ket {000} $, vilket skulle innebära att detta är det enda läget med sannolikheten amplitud i detta läge).</span><span class="sxs-lookup"><span data-stu-id="19305-228">**`|0>:`** this row corresponds to the `0` computational basis state (given that our initial state post-allocation was $\ket{000}$, we would expect this to be the only state with probability amplitude at this point).</span></span>
* <span data-ttu-id="19305-229">**`1.000000 +  0.000000 i`**: sannolikheten amplitud i kartesiska-format.</span><span class="sxs-lookup"><span data-stu-id="19305-229">**`1.000000 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="19305-230">**` == `**: `equal` tecknet separerar båda motsvarande representationer.</span><span class="sxs-lookup"><span data-stu-id="19305-230">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="19305-231">**`********************`**: En grafisk representation av storleken, antalet `*` står i proportion till sannolikheten för att mäta den här tillstånds vektorn.</span><span class="sxs-lookup"><span data-stu-id="19305-231">**`********************`**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span> 
* <span data-ttu-id="19305-232">**`[ 1.000000 ]`**: det numeriska värdet för storlek</span><span class="sxs-lookup"><span data-stu-id="19305-232">**`[ 1.000000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="19305-233">**`    ---`**: En grafisk representation av amplitudens fas.</span><span class="sxs-lookup"><span data-stu-id="19305-233">**`    ---`**: A graphical representation of the amplitude's phase.</span></span>
* <span data-ttu-id="19305-234">**`[ 0.0000 rad ]`**: det numeriska värdet för fasen (i radianer).</span><span class="sxs-lookup"><span data-stu-id="19305-234">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="19305-235">Både storleken och fasen visas med en grafisk representation.</span><span class="sxs-lookup"><span data-stu-id="19305-235">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="19305-236">Representation av storlek är enkel: visar ett fält med `*` och ju högre sannolikhet, desto större är stapeln.</span><span class="sxs-lookup"><span data-stu-id="19305-236">The magnitude representation is straightforward: it shows a bar of `*`, and the higher the probability, the larger the bar will be.</span></span> <span data-ttu-id="19305-237">För fasen, se avsnittet DumpMachine [här](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions) för möjliga symbol representationer baserat på vinkel intervall.</span><span class="sxs-lookup"><span data-stu-id="19305-237">For the phase, see the DumpMachine section [here](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions) for the possible symbol representations based on angle ranges.</span></span>


<span data-ttu-id="19305-238">Den utskrivna utmatningen illustrerar därför att våra programmerade portar omvandlade vår status från</span><span class="sxs-lookup"><span data-stu-id="19305-238">So, the printed output is illustrating that our programmed gates transformed our state from</span></span>

<span data-ttu-id="19305-239">$ $ \ket{\psi} \_ {initial} = \ket {000} $ $</span><span class="sxs-lookup"><span data-stu-id="19305-239">$$ \ket{\psi}\_{initial} = \ket{000} $$</span></span>

<span data-ttu-id="19305-240">till</span><span class="sxs-lookup"><span data-stu-id="19305-240">to</span></span> 

<span data-ttu-id="19305-241">$ $ \begin{align} \ket{\psi} \_ {Final} &= \frac {1} {\sqrt {8} } \left (\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="19305-241">$$ \begin{align} \ket{\psi}\_{final} &= \frac{1}{\sqrt{8}} \left( \ket{000} + \ket{001} + \ket{010} + \ket{011} + \ket{100} + \ket{101} + \ket{110} + \ket{111}  \right) \\\\ &= \frac{1}{\sqrt{2^n}}\sum\_{j=0}^{2^n-1} \ket{j}, \end{align} $$</span></span>

<span data-ttu-id="19305-242">Det är precis som funktionen för transformering av qubit Fourier.</span><span class="sxs-lookup"><span data-stu-id="19305-242">which is precisely the behavior of the 3-qubit Fourier transform.</span></span> 

<span data-ttu-id="19305-243">Om du är nyfiken på hur andra ingångs tillstånd påverkas, rekommenderar vi att du spelar med att använda qubit-åtgärder före transformeringen.</span><span class="sxs-lookup"><span data-stu-id="19305-243">If you are curious about how other input states are affected, we encourage you to play around with applying qubit operations before the transform.</span></span>

## <a name="adding-measurements"></a><span data-ttu-id="19305-244">Lägga till mått</span><span class="sxs-lookup"><span data-stu-id="19305-244">Adding measurements</span></span>

<span data-ttu-id="19305-245">Ett hörn av Quantum Mechanics talar tyvärr om för oss att ett verkligt Quantum-system inte kan ha en sådan `DumpMachine` funktion.</span><span class="sxs-lookup"><span data-stu-id="19305-245">Unfortunately, a cornerstone of quantum mechanics tells us that a real quantum system cannot have such a `DumpMachine` function.</span></span> <span data-ttu-id="19305-246">I stället tvingas vi att extrahera information via mätningar, som i allmänhet inte bara kan ge oss det fullständiga Quantum-läget, men kan också drastiskt ändra själva systemet.</span><span class="sxs-lookup"><span data-stu-id="19305-246">Instead, we're forced to extract information through measurements, which in general not only fail to provide us the full quantum state, but can also drastically alter the system itself.</span></span>
<span data-ttu-id="19305-247">Det finns många olika typer av Quantum-mätningar, men vi fokuserar på de mest grundläggande: projekt måtten för enskilda qubits.</span><span class="sxs-lookup"><span data-stu-id="19305-247">There are many sorts of quantum measurements, but we will focus on the most basic: projective measurements on single qubits.</span></span>
<span data-ttu-id="19305-248">Vid mätning i en specifik grund (t. ex. beräknings basen $ \{ \ket {0} , \ket {1} \} $), projiceras qubit-statusen på det villkor som har mätts---därför att alla överpositioner mellan de två anges.</span><span class="sxs-lookup"><span data-stu-id="19305-248">Upon measurement in a given basis (e.g. the computational basis $ \{ \ket{0}, \ket{1} \} $), the qubit state is projected onto whichever basis state was measured---hence destroying any superposition between the two.</span></span>

<span data-ttu-id="19305-249">För att implementera mätningar i ett Q #-program, använder vi `M` åtgärden (från `Microsoft.Quantum.Intrinsic` ) som returnerar en `Result` typ.</span><span class="sxs-lookup"><span data-stu-id="19305-249">To implement measurements within a Q# program, we use the `M` operation (from `Microsoft.Quantum.Intrinsic`), which returns a `Result` type.</span></span>

<span data-ttu-id="19305-250">Först ändrar vi vår `Perform3QubitQFT` åtgärd för att returnera en matris med mått resultat, `Result[]` i stället för `Unit` .</span><span class="sxs-lookup"><span data-stu-id="19305-250">First, we modify our `Perform3QubitQFT` operation to return an array of measurement results, `Result[]`, instead of `Unit`.</span></span>

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a><span data-ttu-id="19305-251">Definiera och initiera `Result[]` matris</span><span class="sxs-lookup"><span data-stu-id="19305-251">Define and initialize `Result[]` array</span></span>

<span data-ttu-id="19305-252">Innan du ens tilldelar qubits (t. ex. före `using` uttrycket), deklarerar vi och binder denna längd-3-matris (en `Result` för varje qubit):</span><span class="sxs-lookup"><span data-stu-id="19305-252">Before even allocating qubits (i.e. before the `using` statement), we declare and bind this length-3 array (one `Result` for each qubit):</span></span> 

```qsharp
        mutable resultArray = new Result[3];
```

<span data-ttu-id="19305-253">`mutable`Nyckelordet preaktiv `resultArray` tillåter att variabeln binds senare i kod---till exempel när du lägger till våra mått resultat.</span><span class="sxs-lookup"><span data-stu-id="19305-253">The `mutable` keyword prefacing `resultArray` allows the variable to be rebound later in the code---for example, when adding our measurement results.</span></span>

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a><span data-ttu-id="19305-254">Utför mätningar i en `for` slinga och Lägg till resultat i matrisen</span><span class="sxs-lookup"><span data-stu-id="19305-254">Perform measurements in a `for` loop and add results to array</span></span>

<span data-ttu-id="19305-255">Infoga följande kod efter Fourier Transform-åtgärder i `using` blocket:</span><span class="sxs-lookup"><span data-stu-id="19305-255">After the Fourier transform operations inside the `using` block, insert the following code:</span></span>

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
<span data-ttu-id="19305-256">[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)Funktionen som anropas i en matris (t. ex. vår matris av qubits `qs` ) returnerar ett intervall över indexets index.</span><span class="sxs-lookup"><span data-stu-id="19305-256">The [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) function called on an array (e.g. our array of qubits, `qs`) returns a range over the indices of the array.</span></span> <span data-ttu-id="19305-257">Här använder vi den i vår `for` slinga för att sekventiellt mäta varje qubit med hjälp av `M(qs[i])` instruktionen.</span><span class="sxs-lookup"><span data-stu-id="19305-257">Here, we use it in our `for` loop to sequentially measure each qubit using the `M(qs[i])` statement.</span></span>
<span data-ttu-id="19305-258">Varje uppmätt `Result` typ (antingen `Zero` eller `One` ) läggs sedan till i motsvarande index position i `resultArray` med en Update-och-Reassign-instruktion.</span><span class="sxs-lookup"><span data-stu-id="19305-258">Each measured `Result` type (either `Zero` or `One`) is then added to the corresponding index position in `resultArray` with an update-and-reassign statement.</span></span>

> [!NOTE]
> <span data-ttu-id="19305-259">Syntaxen för den här instruktionen är unik för Q #, men motsvarar den liknande variabel omtilldelningen som `resultArray[i] <- M(qs[i])` visas på andra språk, till exempel F # och R.</span><span class="sxs-lookup"><span data-stu-id="19305-259">The syntax of this statement is unique to Q#, but corresponds to the similar variable reassignment `resultArray[i] <- M(qs[i])` seen in other languages such as F# and R.</span></span>

<span data-ttu-id="19305-260">Nyckelordet `set` används alltid för att omtilldela variabler som binds med `mutable` .</span><span class="sxs-lookup"><span data-stu-id="19305-260">The keyword `set` is always used to reassign variables bound using `mutable`.</span></span>

#### <a name="return-resultarray"></a><span data-ttu-id="19305-261">Returrelaterade`resultArray`</span><span class="sxs-lookup"><span data-stu-id="19305-261">Return `resultArray`</span></span>

<span data-ttu-id="19305-262">Med alla tre qubits som mäts och resultaten som har lagts till i `resultArray` , är det säkert att återställa och frigöra qubits som tidigare.</span><span class="sxs-lookup"><span data-stu-id="19305-262">With all three qubits measured and the results added to `resultArray`, we are safe to reset and deallocate the qubits as before.</span></span>
<span data-ttu-id="19305-263">När `using` blockets Stäng visas infogar du</span><span class="sxs-lookup"><span data-stu-id="19305-263">After the `using` block's close, insert</span></span>

```qsharp
        return resultArray;
```
<span data-ttu-id="19305-264">för att slutligen returnera utdata från vår åtgärd.</span><span class="sxs-lookup"><span data-stu-id="19305-264">to ultimately return the output of our operation.</span></span> 

### <a name="understanding-the-effects-of-measurement"></a><span data-ttu-id="19305-265">Förstå effekterna av mått</span><span class="sxs-lookup"><span data-stu-id="19305-265">Understanding the effects of measurement</span></span>

<span data-ttu-id="19305-266">Nu ska vi ändra placeringen av våra `DumpMachine` funktioner för att mata ut tillstånd före och efter mätningarna.</span><span class="sxs-lookup"><span data-stu-id="19305-266">Let's change the placement of our `DumpMachine` functions to output the state before and after the measurements.</span></span>
<span data-ttu-id="19305-267">Den slutgiltiga åtgärds koden bör se ut så här:</span><span class="sxs-lookup"><span data-stu-id="19305-267">The final operation code should look like:</span></span> 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

<span data-ttu-id="19305-268">Om du arbetar från kommando raden skrivs den returnerade matrisen bara ut direkt till-konsolen i slutet av körningen.</span><span class="sxs-lookup"><span data-stu-id="19305-268">If you are working from the command line, the returned array will simply be printed directly to the console at the end of the execution.</span></span>
<span data-ttu-id="19305-269">Annars uppdaterar du värd programmet för att bearbeta den returnerade matrisen.</span><span class="sxs-lookup"><span data-stu-id="19305-269">Otherwise, update your host program to process the returned array.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="19305-270">Kommandorad</span><span class="sxs-lookup"><span data-stu-id="19305-270">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="19305-271">Om du vill ha mer förståelse för den returnerade matrisen som ska skrivas ut i-konsolen kan vi lägga till en annan `Message` i Q #-filen precis innan `return` instruktionen:</span><span class="sxs-lookup"><span data-stu-id="19305-271">To have more understanding of the returned array which will be printed in the console, we can add another `Message` in the Q# file just before the `return` statement:</span></span>

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

<span data-ttu-id="19305-272">Kör projektet och dina utdata bör se ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="19305-272">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[<span data-ttu-id="19305-273">Python</span><span class="sxs-lookup"><span data-stu-id="19305-273">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="19305-274">Uppdatera python-programmet till följande:</span><span class="sxs-lookup"><span data-stu-id="19305-274">Update your Python program to the following:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

<span data-ttu-id="19305-275">Kör filen och dina utdata bör se ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="19305-275">Run the file, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[<span data-ttu-id="19305-276">C#</span><span class="sxs-lookup"><span data-stu-id="19305-276">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="19305-277">Nu när vår åtgärd returnerar ett resultat ersätter du metod anropet `Wait()` med att hämta `Result` egenskapen.</span><span class="sxs-lookup"><span data-stu-id="19305-277">Now that our operation is returning a result, replace the method call `Wait()` with fetching the `Result` property.</span></span> <span data-ttu-id="19305-278">Detta utför fortfarande samma Synchronicity som beskrivs ovan och vi kan binda det här värdet direkt till variabeln `measurementResult` .</span><span class="sxs-lookup"><span data-stu-id="19305-278">This still accomplishes the same synchronicity discussed earlier, and we can directly bind this value to the variable `measurementResult`.</span></span>

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="19305-279">Kör projektet och dina utdata bör se ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="19305-279">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

<span data-ttu-id="19305-280">De här utdata illustrerar några olika saker:</span><span class="sxs-lookup"><span data-stu-id="19305-280">This output illustrates a few different things:</span></span>
1. <span data-ttu-id="19305-281">Om du jämför det returnerade resultatet till för mätningen `DumpMachine` illustreras det tydligt _inte_ efter QFT överpositions tillstånd.</span><span class="sxs-lookup"><span data-stu-id="19305-281">Comparing the returned result to the pre-measurement `DumpMachine`, it clearly does _not_ illustrate the post-QFT superposition over basis states.</span></span>
    <span data-ttu-id="19305-282">En mätning returnerar bara ett enda bas tillstånd, med en sannolikhet som bestäms av amplituden för det aktuella läget i systemets wavefunction.</span><span class="sxs-lookup"><span data-stu-id="19305-282">A measurement only returns a single basis state, with a probability determined by the amplitude of that state in the system's wavefunction.</span></span>
2. <span data-ttu-id="19305-283">Från och med efter mätningen `DumpMachine` ser vi att måttet _ändrar_ själva tillståndet och projicerar det från den ursprungliga överplaceringen för att få till gång till det enskilda tillstånd som motsvarar det uppmätta värdet.</span><span class="sxs-lookup"><span data-stu-id="19305-283">From the post-measurement `DumpMachine`, we see that measurement _changes_ the state itself, projecting it from the initial superposition over basis states to the single basis state that corresponds to the measured value.</span></span>

<span data-ttu-id="19305-284">Om vi skulle upprepa den här åtgärden flera gånger skulle vi se resultat statistiken som börjar illustrera den lika viktade superpositionen för det QFT tillstånd som ger upphov till ett slumpmässigt resultat för varje bild.</span><span class="sxs-lookup"><span data-stu-id="19305-284">If we were to repeat this operation many times, we would see the result statistics begin to illustrate the equally weighted superposition of the post-QFT state that gives rise to a random result on each shot.</span></span>
<span data-ttu-id="19305-285">_Men_förutom att det är ineffektivt och fortfarande är perfekt kan detta dock bara återge de relativa amplituderna i bas staterna, inte de relativa faserna mellan dem.</span><span class="sxs-lookup"><span data-stu-id="19305-285">_However_, besides being inefficient and still imperfect, this would nevertheless only reproduce the relative amplitudes of the basis states, not the relative phases between them.</span></span>
<span data-ttu-id="19305-286">Den senare är inte ett problem i det här exemplet, men vi skulle se att relativa faser visas om du har fått en mer komplex inQFTare än $ \ket {000} $.</span><span class="sxs-lookup"><span data-stu-id="19305-286">The latter is not an issue in this example, but we would see relative phases appear if given a more complex input to the QFT than $\ket{000}$.</span></span>

#### <a name="partial-measurements"></a><span data-ttu-id="19305-287">Partiella mått</span><span class="sxs-lookup"><span data-stu-id="19305-287">Partial measurements</span></span> 
<span data-ttu-id="19305-288">Om du vill utforska hur man mäter att endast vissa qubits av registret kan påverka systemets tillstånd kan du försöka lägga till följande i `for` slingan efter mätnings linjen:</span><span class="sxs-lookup"><span data-stu-id="19305-288">To explore how measuring only some qubits of the register can affect the system's state, try adding the following inside the `for` loop, after the measurement line:</span></span>
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

<span data-ttu-id="19305-289">Observera att `IntAsString` du måste lägga till funktionen för att få åtkomst till funktionen</span><span class="sxs-lookup"><span data-stu-id="19305-289">Note that to access the `IntAsString` function you will have to add</span></span> 
```qsharp
    open Microsoft.Quantum.Convert;
```
<span data-ttu-id="19305-290">med resten av namespace- `open` uttrycken.</span><span class="sxs-lookup"><span data-stu-id="19305-290">with the rest of the namespace `open` statements.</span></span>

<span data-ttu-id="19305-291">I resultatet visas den gradvisa projektionen i del utrymmen som varje qubit mäts.</span><span class="sxs-lookup"><span data-stu-id="19305-291">In the resulting output, you will see the gradual projection into subspaces as each qubit is measured.</span></span>


## <a name="use-the-q-libraries"></a><span data-ttu-id="19305-292">Använd Q #-bibliotek</span><span class="sxs-lookup"><span data-stu-id="19305-292">Use the Q# libraries</span></span>
<span data-ttu-id="19305-293">Som vi nämnde i introduktionen är det mycket av Q #-kraften i det faktum att det gör att du kan ta itu med att hantera enskilda qubits.</span><span class="sxs-lookup"><span data-stu-id="19305-293">As we mentioned in the introduction, much of Q#'s power rests in the fact that it allows you to abstract-away the worries of dealing with individual qubits.</span></span>
<span data-ttu-id="19305-294">Om du vill utveckla fullständiga, tillämpliga Quantum-program, och oroa dig för om en `H` åtgärd går före eller efter en viss rotation, skulle det bara gå långsamt.</span><span class="sxs-lookup"><span data-stu-id="19305-294">Indeed, if you want to develop full-scale, applicable quantum programs, worrying about whether an `H` operation goes before or after a particular rotation would only slow you down.</span></span> 

<span data-ttu-id="19305-295">Q #-biblioteken innehåller [QFT](xref:microsoft.quantum.canon.qft) -åtgärden, som du bara kan ta och använda för valfritt antal qubits.</span><span class="sxs-lookup"><span data-stu-id="19305-295">The Q# libraries contain the [QFT](xref:microsoft.quantum.canon.qft) operation, which you can simply take and apply for any number of qubits.</span></span>
<span data-ttu-id="19305-296">För att ge det ett försök definierar du en ny åtgärd i din Q #-fil som har samma innehåll `Perform3QubitQFT` , men med allt från den första `H` till den `SWAP` ersatt av två enkla rader:</span><span class="sxs-lookup"><span data-stu-id="19305-296">To give it a try, define a new operation in your Q# file which has the same contents of `Perform3QubitQFT`, but with everything from the first `H` to the `SWAP` replaced by two easy lines:</span></span>
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
<span data-ttu-id="19305-297">Den första raden skapar helt enkelt ett [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) uttryck för den allokerade matrisen qubits, `qs` vilket är vad [QFT](xref:microsoft.quantum.canon.qft) -åtgärden tar som ett argument.</span><span class="sxs-lookup"><span data-stu-id="19305-297">The first line simply creates a [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expression of the allocated array of qubits, `qs`, which is what the [QFT](xref:microsoft.quantum.canon.qft) operation takes as an argument.</span></span>
<span data-ttu-id="19305-298">Detta motsvarar index ordningen för qubits i registret.</span><span class="sxs-lookup"><span data-stu-id="19305-298">This corresponds to index ordering of the qubits in the register.</span></span>

<span data-ttu-id="19305-299">Om du vill ha åtkomst till dessa åtgärder lägger du till `open` instruktioner för deras respektive namnrum i början av Q #-filen:</span><span class="sxs-lookup"><span data-stu-id="19305-299">To have access to these operations, add `open` statements for their respective namespaces at the beginning of the Q# file:</span></span>
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

<span data-ttu-id="19305-300">Nu ska du justera värd programmet för att anropa namnet på din nya åtgärd (t. ex. `PerformIntrinsicQFT` ) och ge den ett försök.</span><span class="sxs-lookup"><span data-stu-id="19305-300">Now, adjust your host program to call the name of your new operation (e.g. `PerformIntrinsicQFT`), and give it a whirl.</span></span>

<span data-ttu-id="19305-301">Om du vill se den verkliga fördelen med att använda Q # Library-åtgärder ändrar du antalet qubits till något annat än `3` :</span><span class="sxs-lookup"><span data-stu-id="19305-301">To see the real benefit of using the Q# library operations, change the number of qubits to something other than `3`:</span></span>
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
<span data-ttu-id="19305-302">Du kan därför använda rätt QFT för ett angivet antal qubits, utan att behöva oroa dig för nya `H` åtgärder och rotationer på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="19305-302">You can thus apply the proper QFT for any given number of qubits, without having to worry about the mess of new `H` operations and rotations on each qubit.</span></span>

<span data-ttu-id="19305-303">Observera att Quantum simulatorn tar exponentiellt mer tid att köra när du ökar antalet qubits---exakt varför vi ser fram emot att bli verkligt Quantum-maskinvara!</span><span class="sxs-lookup"><span data-stu-id="19305-303">Note that the quantum simulator takes exponentially more time to run as you increase the number of qubits---precisely why we look forward to real quantum hardware!</span></span>













