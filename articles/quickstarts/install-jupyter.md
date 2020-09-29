---
title: Utveckla med Jupyter Notebooks för Q#
description: Lär dig hur du skapar ett Q#-program med Jupyter Notebooks.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 51de510907ea087d1f23d3ff65d268d6d455a493
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834320"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a><span data-ttu-id="7a358-103">Utveckla med Jupyter Notebooks för Q#</span><span class="sxs-lookup"><span data-stu-id="7a358-103">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="7a358-104">Installera QDK för utveckling av Q#-åtgärder i Jupyter Notebooks för Q#.</span><span class="sxs-lookup"><span data-stu-id="7a358-104">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="7a358-105">Jupyter Notebooks möjliggör kodberäkning på plats och innehåller instruktioner, kommentarer och annat innehåll.</span><span class="sxs-lookup"><span data-stu-id="7a358-105">Jupyter Notebooks allow in-place code computation alongside instructions, notes, and other content.</span></span> <span data-ttu-id="7a358-106">Den här miljön är idealisk när du vill skriva Q#-kod med inbäddade förklaringar eller skapa interaktiva självstudier för kvantberäkning.</span><span class="sxs-lookup"><span data-stu-id="7a358-106">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="7a358-107">Här är det du behöver göra för att börja skapa dina egna Q#-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="7a358-107">Here's what you need to do to start creating your own Q# notebooks.</span></span>

## <a name="install-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="7a358-108">Installera IQ#-Jupyter-kärnan</span><span class="sxs-lookup"><span data-stu-id="7a358-108">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="7a358-109">IQ# (uttalas i-q-sharp) är ett tillägg som främst används av Jupyter och Python i .NET Core SDK, och som ger grundläggande funktioner för att kompilera och simulera Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="7a358-109">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="7a358-110">Installera med hjälp av conda (rekommenderas)</span><span class="sxs-lookup"><span data-stu-id="7a358-110">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="7a358-111">Installera [Miniconda](https://docs.conda.io/en/latest/miniconda.html) eller [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="7a358-111">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="7a358-112">**Obs!** 64-bitarsinstallation krävs.</span><span class="sxs-lookup"><span data-stu-id="7a358-112">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="7a358-113">Öppna en Anaconda-prompt.</span><span class="sxs-lookup"><span data-stu-id="7a358-113">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="7a358-114">Eller om du föredrar att använda PowerShell eller pwsh: öppna ett gränssnitt, kör `conda init powershell`, stäng och öppna sedan gränssnittet igen.</span><span class="sxs-lookup"><span data-stu-id="7a358-114">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="7a358-115">Skapa och aktivera en ny conda-miljö som heter `qsharp-env` med de nödvändiga paketen (inklusive Jupyter Notebook och IQ#) genom att köra följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="7a358-115">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="7a358-116">Kör `python -c "import qsharp"` från samma terminal för att verifiera installationen och fylla i det lokala paketets cacheminne med alla nödvändiga QDK-komponenter.</span><span class="sxs-lookup"><span data-stu-id="7a358-116">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="7a358-117">Installera med hjälp av .NET CLI (avancerat)</span><span class="sxs-lookup"><span data-stu-id="7a358-117">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="7a358-118">Krav:</span><span class="sxs-lookup"><span data-stu-id="7a358-118">Prerequisites:</span></span>

    - <span data-ttu-id="7a358-119">[Python](https://www.python.org/downloads/) 3.6 eller senare</span><span class="sxs-lookup"><span data-stu-id="7a358-119">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="7a358-120">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="7a358-120">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="7a358-121">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="7a358-121">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="7a358-122">Installera `Microsoft.Quantum.IQSharp`-paketet.</span><span class="sxs-lookup"><span data-stu-id="7a358-122">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

> [!NOTE]
> <span data-ttu-id="7a358-123">Om du får ett felmeddelande under `dotnet iqsharp install`-steget, öppnar du ett nytt terminalfönster och försöker igen.</span><span class="sxs-lookup"><span data-stu-id="7a358-123">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
> <span data-ttu-id="7a358-124">Om det fortfarande inte fungerar kan du försöka hitta det installerade `dotnet-iqsharp`-verktyget (i Windows, `dotnet-iqsharp.exe`) och köra:</span><span class="sxs-lookup"><span data-stu-id="7a358-124">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
> ```
> /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
> ```
> <span data-ttu-id="7a358-125">där `/path/to/dotnet-iqsharp` ersätts med den absoluta sökvägen till `dotnet-iqsharp`-verktyget i filsystemet.</span><span class="sxs-lookup"><span data-stu-id="7a358-125">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
> <span data-ttu-id="7a358-126">Den finns vanligtvis under `.dotnet/tools` i användarprofilens mapp.</span><span class="sxs-lookup"><span data-stu-id="7a358-126">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="7a358-127">Klart!</span><span class="sxs-lookup"><span data-stu-id="7a358-127">That's it!</span></span> <span data-ttu-id="7a358-128">Nu har du IQ#-kärnan för Jupyter, som tillhandahåller grundläggande funktioner för kompilering och körning av Q#-åtgärder från Jupyter Notebooks för Q#.</span><span class="sxs-lookup"><span data-stu-id="7a358-128">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and running Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-no-locq-notebook"></a><span data-ttu-id="7a358-129">Skapa din första Q#-notebook</span><span class="sxs-lookup"><span data-stu-id="7a358-129">Create your first Q# notebook</span></span>

<span data-ttu-id="7a358-130">Nu är du redo att verifiera installationen av Jupyter Notebook för Q# genom att skriva och köra en enkel Q#-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="7a358-130">Now you are ready to verify your Q# Jupyter Notebook installation by writing and running a simple Q# operation.</span></span>

1. <span data-ttu-id="7a358-131">Från den miljö som du skapade under installationen (det vill säga antingen den conda-miljö som du skapade eller den Python-miljö där du installerade Jupyter) kör du följande kommando för att starta Jupyter Notebook-servern:</span><span class="sxs-lookup"><span data-stu-id="7a358-131">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="7a358-132">Om Jupyter Notebook inte öppnas automatiskt i webbläsaren kopierar och klistrar du in den URL som finns på kommandoraden till webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="7a358-132">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="7a358-133">Välj **Ny → Q#** för att skapa en Jupyter Notebook med en Q#-kernel, och lägg till följande kod i den första Notebook-cellen:</span><span class="sxs-lookup"><span data-stu-id="7a358-133">Choose **New → Q#** to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="7a358-134">Kör följande Notebook-cell:</span><span class="sxs-lookup"><span data-stu-id="7a358-134">Run this cell of the notebook:</span></span>

    ![Jupyter Notebook-cell med Q#-kod](~/media/install-guide-jupyter.png)

    <span data-ttu-id="7a358-136">Du bör se `SampleQuantumRandomNumberGenerator` i cellens utdata.</span><span class="sxs-lookup"><span data-stu-id="7a358-136">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="7a358-137">När du kör Jupyter Notebook kompileras Q#-koden, och cellen visar namnet på eventuella åtgärder som den hittar.</span><span class="sxs-lookup"><span data-stu-id="7a358-137">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="7a358-138">I en ny cell kör du den åtgärd som du nyss skapade (i en simulator) med kommandot `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="7a358-138">In a new cell, run the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![Jupyter Notebook-cell med %simulate magic](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="7a358-140">Du bör se resultatet av den åtgärd du anropade.</span><span class="sxs-lookup"><span data-stu-id="7a358-140">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="7a358-141">Eftersom åtgärden genererar ett slumpmässigt resultat visas i det här fallet antingen `Zero` eller `One` på skärmen.</span><span class="sxs-lookup"><span data-stu-id="7a358-141">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="7a358-142">Om du kör cellen upprepade gånger bör du se varje resultat ungefär varannan gång.</span><span class="sxs-lookup"><span data-stu-id="7a358-142">If you run the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7a358-143">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="7a358-143">Next steps</span></span>

<span data-ttu-id="7a358-144">Nu när du har installerat QDK för Q#-Jupyter Notebooks kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng) genom att skriva Q#-kod direkt i Jupyter Notebook-miljön.</span><span class="sxs-lookup"><span data-stu-id="7a358-144">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="7a358-145">Fler exempel på vad du kan göra med Q#-Jupyter Notebooks finns i:</span><span class="sxs-lookup"><span data-stu-id="7a358-145">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="7a358-146">[Introduktion till Q# och Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="7a358-146">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="7a358-147">Där finns en Q#-Jupyter Notebook med mer information om hur du använder Q# i Jupyter-miljön.</span><span class="sxs-lookup"><span data-stu-id="7a358-147">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="7a358-148">[Quantum Katas](xref:microsoft.quantum.overview.katas) är en samling självstudier och uppsättningar med programmeringsövningar med öppen källkod i form av Q#-Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="7a358-148">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="7a358-149">Det kan vara bra att börja med [Quantum Katas-självstudiernas notebook-filer](https://github.com/microsoft/QuantumKatas#tutorial-topics).</span><span class="sxs-lookup"><span data-stu-id="7a358-149">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="7a358-150">I Quantum Katas lär du dig både kvantberäkning och Q#-programmering på samma gång.</span><span class="sxs-lookup"><span data-stu-id="7a358-150">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="7a358-151">De är ett utmärkt exempel på den typ av innehåll du kan skapa med Q#-Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="7a358-151">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
