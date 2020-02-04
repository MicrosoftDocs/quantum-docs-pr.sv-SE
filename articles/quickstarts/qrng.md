---
title: Skapa en kvantgenerator för slumptal
description: Skapa ett Q#-projekt som demonstrerar grundläggande kvantbegrepp som t.ex. superposition genom att skapa en kvantgenerator för slumptal.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 134617455b720cc755b9ee9fb68fb59e624d3f1a
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820948"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="46337-103">Snabbstart: Implementera en kvantgenerator för slumptal i Q#</span><span class="sxs-lookup"><span data-stu-id="46337-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="46337-104">Ett enkelt exempel på en kvantalgoritm som skrivs i Q# och som är en kvantgenerator för slumptal.</span><span class="sxs-lookup"><span data-stu-id="46337-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="46337-105">Den här algoritmen använder kvantmekanik till att generera ett slumptal.</span><span class="sxs-lookup"><span data-stu-id="46337-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="46337-106">Krav</span><span class="sxs-lookup"><span data-stu-id="46337-106">Prerequisites</span></span>

- <span data-ttu-id="46337-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="46337-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="46337-108">Skapa ett Q#-projekt</span><span class="sxs-lookup"><span data-stu-id="46337-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="46337-109">Skriv en Q#-åtgärd</span><span class="sxs-lookup"><span data-stu-id="46337-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="46337-110">Q#-åtgärdskod</span><span class="sxs-lookup"><span data-stu-id="46337-110">Q# operation code</span></span>

1. <span data-ttu-id="46337-111">Ersätt innehållet i filen Operation.qs med följande kod:</span><span class="sxs-lookup"><span data-stu-id="46337-111">Replace the contents of the Operation.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(qubit = Qubit())  { // Allocate a qubit.
                H(qubit);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(v);     // Measure the qubit value.
                Reset(qubit);
                return r;
            }
        }
    }
    ```

<span data-ttu-id="46337-112">Som vi nämnde i artikeln [Vad är kvantberäkning?](xref:microsoft.quantum.overview.what) är en kvantbit en enhet av kvantinformation som kan vara i superposition.</span><span class="sxs-lookup"><span data-stu-id="46337-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="46337-113">När den mäts kan kvantbiten endast vara antingen 0 eller 1.</span><span class="sxs-lookup"><span data-stu-id="46337-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="46337-114">Under körningen representerar dock tillståndet för kvantbiten sannolikheten för att avläsningen blir antingen 0 eller 1 vid en mätning.</span><span class="sxs-lookup"><span data-stu-id="46337-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="46337-115">Detta sannolikhetstillstånd kallas för superposition.</span><span class="sxs-lookup"><span data-stu-id="46337-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="46337-116">Vi kan använda sannolikheten till att generera slumpmässiga tal.</span><span class="sxs-lookup"><span data-stu-id="46337-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="46337-117">I vår Q#-åtgärd introducerar vi `Qubit`-datatypen, som ingår i Q#.</span><span class="sxs-lookup"><span data-stu-id="46337-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="46337-118">Vi kan bara allokera en `Qubit` med en `using`-instruktion.</span><span class="sxs-lookup"><span data-stu-id="46337-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="46337-119">När den tilldelas är kvantbiten alltid  i `Zero`-tillståndet.</span><span class="sxs-lookup"><span data-stu-id="46337-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="46337-120">Med hjälp av `H`-åtgärden kan vi försätta vår `Qubit` i superposition.</span><span class="sxs-lookup"><span data-stu-id="46337-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="46337-121">Om du vill mäta en kvantbit och läsa dess värde, använder du den inbäddade `M`-åtgärden.</span><span class="sxs-lookup"><span data-stu-id="46337-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="46337-122">Genom att försätta vår `Qubit` i superposition och mäta den, kommer vårt resultat att bli ett annat värde varje gången koden anropas.</span><span class="sxs-lookup"><span data-stu-id="46337-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="46337-123">När en `Qubit` har frigjorts måste den försättas i `Zero`-tillståndet igen, annars rapporteras ett körningsfel i simulatorn.</span><span class="sxs-lookup"><span data-stu-id="46337-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="46337-124">Ett enkelt sätt att göra detta på är att anropa `Reset`.</span><span class="sxs-lookup"><span data-stu-id="46337-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="46337-125">Visualisera koden med Bloch-sfären</span><span class="sxs-lookup"><span data-stu-id="46337-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="46337-126">I Bloch-sfären representerar nordpolen det klassiska värdet **0** och sydpolen det klassiska värdet **1**.</span><span class="sxs-lookup"><span data-stu-id="46337-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="46337-127">Alla superpositioner kan representeras av en punkt på sfären (visas med en pil).</span><span class="sxs-lookup"><span data-stu-id="46337-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="46337-128">Ju närmare pilen är en pol, desto högre är sannolikheten att kvantbiten minimeras till det klassiska värde som tilldelades till polen när den mättes.</span><span class="sxs-lookup"><span data-stu-id="46337-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="46337-129">Kvantbitstillståndet som representeras av den röda pilen nedan har till exempel en högre sannolikhet att ge värdet **0** om vi mäter det.</span><span class="sxs-lookup"><span data-stu-id="46337-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175">

<span data-ttu-id="46337-130">Vi kan använda den här representationen till att visualisera vad koden gör:</span><span class="sxs-lookup"><span data-stu-id="46337-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="46337-131">Först börjar vi med en kvantbit som initierats i tillståndet **0**. Vi använder `H` till att skapa en superposition där sannolikheten för **0** och **1** är densamma.</span><span class="sxs-lookup"><span data-stu-id="46337-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450">

* <span data-ttu-id="46337-132">Sedan mäter vi kvantbiten och sparar utdatan:</span><span class="sxs-lookup"><span data-stu-id="46337-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450">

<span data-ttu-id="46337-133">Eftersom resultatet av mätningen är helt slumpmässigt har vi fått en slumpmässig bit.</span><span class="sxs-lookup"><span data-stu-id="46337-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="46337-134">Vi kan anropa den här åtgärden flera gånger för att skapa heltal.</span><span class="sxs-lookup"><span data-stu-id="46337-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="46337-135">Om vi till exempel anropar åtgärden tre gånger för att få tre slumpmässiga bitar, kan vi bygga slumpmässiga 3-bitarstal (det vill säga ett slumptal mellan 0 och 7).</span><span class="sxs-lookup"><span data-stu-id="46337-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a><span data-ttu-id="46337-136">Skapa en komplett slumptalsgenerator med ett värdprogram</span><span class="sxs-lookup"><span data-stu-id="46337-136">Creating a complete random number generator using a host program</span></span>

<span data-ttu-id="46337-137">Nu när vi har en Q#-åtgärd som genererar slumpmässiga bitar, kan vi använda den till att skapa en komplett slumptalsgenerator med ett värdprogram.</span><span class="sxs-lookup"><span data-stu-id="46337-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator with a host program.</span></span>

 ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[<span data-ttu-id="46337-138">Python med Visual Studio Code eller kommandoraden</span><span class="sxs-lookup"><span data-stu-id="46337-138">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)
 
 <span data-ttu-id="46337-139">Om du vill köra ditt nya Q#-program från Python sparar du följande kod som `host.py`:</span><span class="sxs-lookup"><span data-stu-id="46337-139">To run your new Q# program from Python, save the following code as `host.py`:</span></span>
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 <span data-ttu-id="46337-140">Du kan sedan köra Python-värdprogrammet från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="46337-140">You can then run your Python host program from the command line:</span></span>
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[<span data-ttu-id="46337-141">C# med Visual Studio Code eller kommandoraden</span><span class="sxs-lookup"><span data-stu-id="46337-141">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)
 
 <span data-ttu-id="46337-142">Om du vill köra ditt nya Q#-program från C# ändrar du `Driver.cs` så att följande C#-kod ingår:</span><span class="sxs-lookup"><span data-stu-id="46337-142">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 <span data-ttu-id="46337-143">Du kan sedan köra C#-värdprogrammet från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="46337-143">You can then run your C# host program from the command line:</span></span>
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="46337-144">C# med Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="46337-144">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

 <span data-ttu-id="46337-145">Om du vill köra ditt nya Q#-program från C# i Visual Studio ändrar du `Driver.cs` så att följande C#-kod ingår:</span><span class="sxs-lookup"><span data-stu-id="46337-145">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 <span data-ttu-id="46337-146">Därefter trycker du på F5. Programmet startas och ett nytt fönster öppnas med det genererade slumptalet:</span><span class="sxs-lookup"><span data-stu-id="46337-146">Then press F5, the program will start execution and a new window will pop up with the random number generated:</span></span> 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
