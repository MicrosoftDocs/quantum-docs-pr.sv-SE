---
title: Skapa en kvantgenerator för slumptal
description: Skapa ett Q# projekt som visar grundläggande Quantum-koncept som överposition genom att skapa en Quantum slump tals Generator.
author: bromeg
ms.author: megbrow
ms.date: 10/25/2019
ms.topic: tutorial
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: f36db426a8f0479580117cce44a67ad3a053d5de
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856354"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="69262-103">Självstudier: Implementera en kvantgenerator för slumptal i Q\#</span><span class="sxs-lookup"><span data-stu-id="69262-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="69262-104">Ett enkelt exempel på en Quantum-algoritm som Q# är skrivet i är en Quantum slump tals Generator.</span><span class="sxs-lookup"><span data-stu-id="69262-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="69262-105">Den här algoritmen använder kvantmekanik till att generera ett slumptal.</span><span class="sxs-lookup"><span data-stu-id="69262-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="69262-106">Krav</span><span class="sxs-lookup"><span data-stu-id="69262-106">Prerequisites</span></span>

- <span data-ttu-id="69262-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="69262-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="69262-108">Skapa ett Q# projekt för antingen ett [ Q# program](xref:microsoft.quantum.install.standalone), med ett [python-värdprogram](xref:microsoft.quantum.install.python)eller ett [C#-värd program](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="69262-108">Create a Q# project for either a [Q# application](xref:microsoft.quantum.install.standalone), with a [Python host program](xref:microsoft.quantum.install.python), or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="write-a-no-locq-operation"></a><span data-ttu-id="69262-109">Skriv en Q# åtgärd</span><span class="sxs-lookup"><span data-stu-id="69262-109">Write a Q# operation</span></span>

### <a name="no-locq-operation-code"></a><span data-ttu-id="69262-110">Q# åtgärds kod</span><span class="sxs-lookup"><span data-stu-id="69262-110">Q# operation code</span></span>

1. <span data-ttu-id="69262-111">Ersätt innehållet i filen Program.qs med följande kod:</span><span class="sxs-lookup"><span data-stu-id="69262-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="69262-112">Som vi nämnde i artikeln [Så här fungerar kvantberäkning](xref:microsoft.quantum.overview.understanding) är en kvantbit en enhet för kvantinformation som kan vara i superposition.</span><span class="sxs-lookup"><span data-stu-id="69262-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="69262-113">När den mäts kan kvantbiten endast vara antingen 0 eller 1.</span><span class="sxs-lookup"><span data-stu-id="69262-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="69262-114">Före mätningen representerar dock qubit tillstånd sannolikheten för att läsa antingen 0 eller 1 med ett mått.</span><span class="sxs-lookup"><span data-stu-id="69262-114">However, before measurement, the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="69262-115">Detta sannolikhetstillstånd kallas för superposition.</span><span class="sxs-lookup"><span data-stu-id="69262-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="69262-116">Vi kan använda sannolikheten till att generera slumpmässiga tal.</span><span class="sxs-lookup"><span data-stu-id="69262-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="69262-117">I vår Q# åtgärd introducerar vi `Qubit` data typen, intern för Q# .</span><span class="sxs-lookup"><span data-stu-id="69262-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="69262-118">Vi kan bara allokera en `Qubit` med en `using`-instruktion.</span><span class="sxs-lookup"><span data-stu-id="69262-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="69262-119">När den tilldelas är kvantbiten alltid  i `Zero`-tillståndet.</span><span class="sxs-lookup"><span data-stu-id="69262-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="69262-120">Med hjälp av `H`-åtgärden kan vi försätta vår `Qubit` i superposition.</span><span class="sxs-lookup"><span data-stu-id="69262-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="69262-121">Om du vill mäta en kvantbit och läsa dess värde, använder du den inbäddade `M`-åtgärden.</span><span class="sxs-lookup"><span data-stu-id="69262-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="69262-122">Genom att försätta vår `Qubit` i superposition och mäta den, kommer vårt resultat att bli ett annat värde varje gången koden anropas.</span><span class="sxs-lookup"><span data-stu-id="69262-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="69262-123">När en `Qubit` har frigjorts måste den försättas i `Zero`-tillståndet igen. Annars rapporteras ett körningsfel i simulatorn.</span><span class="sxs-lookup"><span data-stu-id="69262-123">When a `Qubit` is deallocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="69262-124">Ett enkelt sätt att göra detta på är att anropa `Reset`.</span><span class="sxs-lookup"><span data-stu-id="69262-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="69262-125">Visualisera koden med Bloch-sfären</span><span class="sxs-lookup"><span data-stu-id="69262-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="69262-126">I Bloch-sfären representerar nordpolen det klassiska värdet **0** och sydpolen det klassiska värdet **1**.</span><span class="sxs-lookup"><span data-stu-id="69262-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="69262-127">Alla superpositioner kan representeras av en punkt på sfären (visas med en pil).</span><span class="sxs-lookup"><span data-stu-id="69262-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="69262-128">Ju närmare pilen är en pol, desto högre är sannolikheten att kvantbiten minimeras till det klassiska värde som tilldelades till polen när den mättes.</span><span class="sxs-lookup"><span data-stu-id="69262-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="69262-129">Kvantbitstillståndet som representeras av den röda pilen nedan har till exempel en högre sannolikhet att ge värdet **0** om vi mäter det.</span><span class="sxs-lookup"><span data-stu-id="69262-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="69262-130">Vi kan använda den här representationen till att visualisera vad koden gör:</span><span class="sxs-lookup"><span data-stu-id="69262-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="69262-131">Först börjar vi med en kvantbit som initierats i tillståndet **0**. Vi använder `H` till att skapa en superposition där sannolikheten för **0** och **1** är densamma.</span><span class="sxs-lookup"><span data-stu-id="69262-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="69262-132">Sedan mäter vi kvantbiten och sparar utdatan:</span><span class="sxs-lookup"><span data-stu-id="69262-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="69262-133">Eftersom resultatet av mätningen är helt slumpmässigt har vi fått en slumpmässig bit.</span><span class="sxs-lookup"><span data-stu-id="69262-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="69262-134">Vi kan anropa den här åtgärden flera gånger för att skapa heltal.</span><span class="sxs-lookup"><span data-stu-id="69262-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="69262-135">Om vi till exempel anropar åtgärden tre gånger för att få tre slumpmässiga bitar, kan vi bygga slumpmässiga 3-bitarstal (det vill säga ett slumptal mellan 0 och 7).</span><span class="sxs-lookup"><span data-stu-id="69262-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="69262-136">Skapa en komplett slumptalsgenerator</span><span class="sxs-lookup"><span data-stu-id="69262-136">Creating a complete random number generator</span></span>

<span data-ttu-id="69262-137">Nu när vi har en Q# åtgärd som genererar slumpmässiga bitar kan vi använda den för att bygga en komplett Quantum slump tals Generator.</span><span class="sxs-lookup"><span data-stu-id="69262-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="69262-138">Vi kan använda ett Q# program eller använda ett värd program.</span><span class="sxs-lookup"><span data-stu-id="69262-138">We can use a Q# application or use a host program.</span></span>



### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="69262-139">Q# program med Visual Studio eller Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="69262-139">Q# applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="69262-140">Om du vill skapa hela Q# programmet lägger du till följande start punkt i Q# programmet:</span><span class="sxs-lookup"><span data-stu-id="69262-140">To create the full Q# application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="69262-141">Programmet kommer att köra åtgärden eller funktionen som marker ATS med `@EntryPoint()` attributet på en simulator eller resurs uppskattning, beroende på projekt konfigurationen och kommando rads alternativen.</span><span class="sxs-lookup"><span data-stu-id="69262-141">The program will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="69262-142">I Visual Studio trycker du helt enkelt på Ctrl + F5 för att köra skriptet.</span><span class="sxs-lookup"><span data-stu-id="69262-142">In Visual Studio, simply press Ctrl + F5 to run the script.</span></span>

<span data-ttu-id="69262-143">Skapa Program.qs första gången genom att skriva följande i terminalfönstret i VS Code:</span><span class="sxs-lookup"><span data-stu-id="69262-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="69262-144">För efterföljande körningar behöver du inte bygga det igen.</span><span class="sxs-lookup"><span data-stu-id="69262-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="69262-145">Du kör det bara genom att skriva följande kommando och trycka på Retur:</span><span class="sxs-lookup"><span data-stu-id="69262-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-prompt"></a>[<span data-ttu-id="69262-146">Python med Visual Studio Code eller kommando tolken</span><span class="sxs-lookup"><span data-stu-id="69262-146">Python with Visual Studio Code or the command prompt</span></span>](#tab/tabid-python)

<span data-ttu-id="69262-147">Om du vill köra det nya Q# programmet från python sparar du följande kod som `host.py` :</span><span class="sxs-lookup"><span data-stu-id="69262-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="69262-148">Du kan sedan köra python-värd programmet från kommando tolken:</span><span class="sxs-lookup"><span data-stu-id="69262-148">You can then run your Python host program from the command prompt:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="69262-149">C# med Visual Studio Code eller Visual Studio</span><span class="sxs-lookup"><span data-stu-id="69262-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="69262-150">Om du vill köra det nya Q# programmet från C# ändrar `Driver.cs` du till att inkludera följande C#-kod:</span><span class="sxs-lookup"><span data-stu-id="69262-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="69262-151">Du kan sedan köra C#-värd programmet från kommando tolken (i Visual Studio bör du trycka på F5):</span><span class="sxs-lookup"><span data-stu-id="69262-151">You can then run your C# host program from the command prompt (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***
