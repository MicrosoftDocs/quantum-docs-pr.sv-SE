---
title: Skapa en kvantgenerator för slumptal
description: Skapa ett Q#-projekt som demonstrerar grundläggande kvantbegrepp som t.ex. superposition genom att skapa en kvantgenerator för slumptal.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: a7c077eda3e46430cbe6598cb899adb460451f75
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443927"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="42ea1-103">Snabbstart: Implementera en kvantgenerator för slumptal i Q#</span><span class="sxs-lookup"><span data-stu-id="42ea1-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="42ea1-104">Ett enkelt exempel på en kvantalgoritm som skrivs i Q# och som är en kvantgenerator för slumptal.</span><span class="sxs-lookup"><span data-stu-id="42ea1-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="42ea1-105">Den här algoritmen använder kvantmekanik till att generera ett slumptal.</span><span class="sxs-lookup"><span data-stu-id="42ea1-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="42ea1-106">Nödvändiga komponenter</span><span class="sxs-lookup"><span data-stu-id="42ea1-106">Prerequisites</span></span>

- <span data-ttu-id="42ea1-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="42ea1-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="42ea1-108">Skapa ett Q#-projekt</span><span class="sxs-lookup"><span data-stu-id="42ea1-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="42ea1-109">Skriv en Q#-åtgärd</span><span class="sxs-lookup"><span data-stu-id="42ea1-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="42ea1-110">Q#-åtgärdskod</span><span class="sxs-lookup"><span data-stu-id="42ea1-110">Q# operation code</span></span>

1. <span data-ttu-id="42ea1-111">Ersätt innehållet i filen Operation.qs med följande kod:</span><span class="sxs-lookup"><span data-stu-id="42ea1-111">Replace the contents of the Operation.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

<span data-ttu-id="42ea1-112">Som vi nämnde i artikeln [Vad är kvantberäkning?](xref:microsoft.quantum.overview.what) är en kvantbit en enhet av kvantinformation som kan vara i superposition.</span><span class="sxs-lookup"><span data-stu-id="42ea1-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="42ea1-113">När den mäts kan kvantbiten endast vara antingen 0 eller 1.</span><span class="sxs-lookup"><span data-stu-id="42ea1-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="42ea1-114">Under körningen representerar dock tillståndet för kvantbiten sannolikheten för att avläsningen blir antingen 0 eller 1 vid en mätning.</span><span class="sxs-lookup"><span data-stu-id="42ea1-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="42ea1-115">Detta sannolikhetstillstånd kallas för superposition.</span><span class="sxs-lookup"><span data-stu-id="42ea1-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="42ea1-116">Vi kan använda sannolikheten till att generera slumpmässiga tal.</span><span class="sxs-lookup"><span data-stu-id="42ea1-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="42ea1-117">I vår Q#-åtgärd introducerar vi `Qubit`-datatypen, som ingår i Q#.</span><span class="sxs-lookup"><span data-stu-id="42ea1-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="42ea1-118">Vi kan bara allokera en `Qubit` med en `using`-instruktion.</span><span class="sxs-lookup"><span data-stu-id="42ea1-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="42ea1-119">När den tilldelas är kvantbiten alltid  i `Zero`-tillståndet.</span><span class="sxs-lookup"><span data-stu-id="42ea1-119">When it gets allocated a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="42ea1-120">Med hjälp av `H`-åtgärden kan vi försätta vår `Qubit` i superposition.</span><span class="sxs-lookup"><span data-stu-id="42ea1-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="42ea1-121">Om du vill mäta en kvantbit och läsa dess värde, använder du den inbäddade `M`-åtgärden.</span><span class="sxs-lookup"><span data-stu-id="42ea1-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="42ea1-122">Genom att försätta vår `Qubit` i superposition och mäta den, kommer vårt resultat att bli ett annat värde varje gången koden anropas.</span><span class="sxs-lookup"><span data-stu-id="42ea1-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="42ea1-123">När en `Qubit` har frigjorts måste den försättas i `Zero`-tillståndet igen, annars rapporteras ett körningsfel i simulatorn.</span><span class="sxs-lookup"><span data-stu-id="42ea1-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="42ea1-124">Ett enkelt sätt att göra detta på är att anropa `Reset`.</span><span class="sxs-lookup"><span data-stu-id="42ea1-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="42ea1-125">Visualisera koden med Bloch-sfären</span><span class="sxs-lookup"><span data-stu-id="42ea1-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="42ea1-126">I Bloch-sfären representerar nordpolen det klassiska värdet **0** och sydpolen det klassiska värdet **1**.</span><span class="sxs-lookup"><span data-stu-id="42ea1-126">In the Bloch sphere the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="42ea1-127">Alla superpositioner kan representeras av en punkt på sfären (visas med en pil).</span><span class="sxs-lookup"><span data-stu-id="42ea1-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="42ea1-128">Ju närmare pilen är en pol, desto högre är sannolikheten att kvantbiten minimeras till det klassiska värde som tilldelades till polen när den mättes.</span><span class="sxs-lookup"><span data-stu-id="42ea1-128">When the closer the end of the arrow to a pole, the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="42ea1-129">Kvantbitstillståndet som representeras av den röda pilen nedan har till exempel en högre sannolikhet att ge värdet **0** om vi mäter det.</span><span class="sxs-lookup"><span data-stu-id="42ea1-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="./Bloch.svg" width="175">

<span data-ttu-id="42ea1-130">Vi kan använda den här representationen till att visualisera vad koden gör:</span><span class="sxs-lookup"><span data-stu-id="42ea1-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="42ea1-131">Först börjar vi med en kvantbit som initierats i tillståndet **0**. Vi använder `H` till att skapa en superposition där sannolikheten för **0** och **1** är densamma.</span><span class="sxs-lookup"><span data-stu-id="42ea1-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="./H.svg" width="450">

* <span data-ttu-id="42ea1-132">Sedan mäter vi kvantbiten och sparar utdatan:</span><span class="sxs-lookup"><span data-stu-id="42ea1-132">Then we measure the qubit and save the output:</span></span>

<img src="./Measurement2.svg" width="450">

<span data-ttu-id="42ea1-133">Eftersom resultatet av mätningen är helt slumpmässigt har vi fått en slumpmässig bit.</span><span class="sxs-lookup"><span data-stu-id="42ea1-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="42ea1-134">Vi kan anropa den här funktionen flera gånger för att skapa heltal.</span><span class="sxs-lookup"><span data-stu-id="42ea1-134">We can call this function several times to create integers.</span></span> <span data-ttu-id="42ea1-135">Om vi till exempel anropar funktionen tre gånger för att få tre slumpmässiga bitar, kan vi bygga slumpmässiga 3-bitarstal (det vill säga ett slumptal mellan 0 och 7).</span><span class="sxs-lookup"><span data-stu-id="42ea1-135">For example, if we call the function three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>
