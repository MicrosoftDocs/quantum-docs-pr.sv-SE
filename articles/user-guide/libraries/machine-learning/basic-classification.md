---
title: Grundläggande klassificering med Quantum Machine Learning-biblioteket
description: Lär dig hur du kör en Quantum-följd som skrivits i Q# med hjälp av quantum Machine Learning-biblioteket för Microsoft-QDK.
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4fe686a87fbdc610badc0bbcbc0bf7b065e0bce9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854048"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="9d67c-103">Grundläggande klassificering: klassificera data med QDK</span><span class="sxs-lookup"><span data-stu-id="9d67c-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="9d67c-104">I den här snabb starten får du lära dig hur du kör en Quantum-klassificerare som skrivits i Q# med quantum Machine Learning-biblioteket för QDK.</span><span class="sxs-lookup"><span data-stu-id="9d67c-104">In this Quickstart, you will learn how to run a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="9d67c-105">I den här hand boken kommer vi att använda den halva måne-datauppsättningen med en klassificerings struktur som definierats i Q# .</span><span class="sxs-lookup"><span data-stu-id="9d67c-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d67c-106">Krav</span><span class="sxs-lookup"><span data-stu-id="9d67c-106">Prerequisites</span></span>

- <span data-ttu-id="9d67c-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="9d67c-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="9d67c-108">Skapa ett Q# projekt för antingen ett [python-värdprogram](xref:microsoft.quantum.install.python) eller ett [C#-värd program](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="9d67c-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="9d67c-109">Värd program</span><span class="sxs-lookup"><span data-stu-id="9d67c-109">Host program</span></span>

<span data-ttu-id="9d67c-110">Ditt värd program består av tre delar:</span><span class="sxs-lookup"><span data-stu-id="9d67c-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="9d67c-111">Läs in data uppsättningen och välj en uppsättning start parametrar för din modell.</span><span class="sxs-lookup"><span data-stu-id="9d67c-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="9d67c-112">Kör träning för att fastställa modellens parametrar och förskjutning.</span><span class="sxs-lookup"><span data-stu-id="9d67c-112">Run training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="9d67c-113">Validera modellen för att fastställa dess exakthet</span><span class="sxs-lookup"><span data-stu-id="9d67c-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="9d67c-114">Python med Visual Studio Code eller kommandoraden</span><span class="sxs-lookup"><span data-stu-id="9d67c-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="9d67c-115">Om du vill köra du är Q# klassificeraren från python sparar du följande kod som `host.py` .</span><span class="sxs-lookup"><span data-stu-id="9d67c-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="9d67c-116">Kom ihåg att du även behöver Q# filen `Training.qs` som beskrivs senare i den här självstudien.</span><span class="sxs-lookup"><span data-stu-id="9d67c-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="9d67c-117">Du kan sedan köra Python-värdprogrammet från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="9d67c-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="9d67c-118">C# med Visual Studio Code eller kommandoraden</span><span class="sxs-lookup"><span data-stu-id="9d67c-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="9d67c-119">Om du vill köra du är Q# klassificeraren från C# sparar du följande kod som `Host.cs` .</span><span class="sxs-lookup"><span data-stu-id="9d67c-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="9d67c-120">Kom ihåg att du även behöver Q# filen `Training.qs` som beskrivs senare i den här självstudien.</span><span class="sxs-lookup"><span data-stu-id="9d67c-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="9d67c-121">Du kan sedan köra C#-värdprogrammet från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="9d67c-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="9d67c-122">C# med Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="9d67c-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="9d67c-123">Om du vill köra det nya Q# programmet från C# i Visual Studio ändrar `Host.cs` du till att inkludera följande C#-kod.</span><span class="sxs-lookup"><span data-stu-id="9d67c-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="9d67c-124">Kom ihåg att du även behöver Q# filen `Training.qs` som beskrivs senare i den här självstudien.</span><span class="sxs-lookup"><span data-stu-id="9d67c-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="9d67c-125">Tryck på F5 och programmet kommer att börja köras.</span><span class="sxs-lookup"><span data-stu-id="9d67c-125">Press F5, and the program will start to run.</span></span> <span data-ttu-id="9d67c-126">Ett nytt fönster visar följande resultat:</span><span class="sxs-lookup"><span data-stu-id="9d67c-126">A new window will display the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="9d67c-127">Q- \# klassificerings kod</span><span class="sxs-lookup"><span data-stu-id="9d67c-127">Q\# classifier code</span></span>

<span data-ttu-id="9d67c-128">Nu ska vi se hur de åtgärder som anropas av värd programmet definieras i Q# .</span><span class="sxs-lookup"><span data-stu-id="9d67c-128">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="9d67c-129">Vi sparar följande kod i en fil med namnet `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="9d67c-129">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="9d67c-130">De viktigaste funktionerna och åtgärderna som definieras i koden ovan är:</span><span class="sxs-lookup"><span data-stu-id="9d67c-130">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="9d67c-131">`ClassifierStructure() : ControlledRotation[]` : i den här funktionen ställer vi in strukturen för vår krets modell genom att lägga till lagren i de kontrollerade portar som vi anser.</span><span class="sxs-lookup"><span data-stu-id="9d67c-131">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="9d67c-132">Det här steget är detsamma som deklarationen av lager i neurons i en sekventiell djup inlärnings modell.</span><span class="sxs-lookup"><span data-stu-id="9d67c-132">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="9d67c-133">`TrainHalfMoonModel() : (Double[], Double)` : den här åtgärden är den grundläggande delen av koden och definierar utbildningen.</span><span class="sxs-lookup"><span data-stu-id="9d67c-133">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="9d67c-134">Här läser vi in exemplen från data uppsättningen som ingår i biblioteket, vi ställer in Hyper-parametrarna och de ursprungliga parametrarna för utbildningen och vi startar utbildningen genom att anropa åtgärden som `TrainSequentialClassifier` ingår i biblioteket.</span><span class="sxs-lookup"><span data-stu-id="9d67c-134">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="9d67c-135">Den matar ut parametrarna och den förskjutning som avgör klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="9d67c-135">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="9d67c-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : den här åtgärden definierar verifierings processen för att utvärdera modellen.</span><span class="sxs-lookup"><span data-stu-id="9d67c-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="9d67c-137">Här läser vi in exemplen för verifiering, antalet mätningar per prov och toleransen.</span><span class="sxs-lookup"><span data-stu-id="9d67c-137">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="9d67c-138">Den ger ut antalet felklassificeringar för den valda batchen över exempel för verifiering.</span><span class="sxs-lookup"><span data-stu-id="9d67c-138">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9d67c-139">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9d67c-139">Next steps</span></span>

<span data-ttu-id="9d67c-140">Först kan du spela med koden och försöka ändra vissa parametrar för att se hur den påverkar utbildningen.</span><span class="sxs-lookup"><span data-stu-id="9d67c-140">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="9d67c-141">I nästa självstudie utformar du sedan [din egen klassificerare](xref:microsoft.quantum.libraries.machine-learning.design)och du får lära dig hur du definierar klassificerarens struktur.</span><span class="sxs-lookup"><span data-stu-id="9d67c-141">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
