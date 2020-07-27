---
title: Utveckla med Q# och Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: ec5e66e0c85d89888a8ff1e7d6bf18bf89ff44ac
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871594"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="a8ff2-102">Utveckla med Q# och Python</span><span class="sxs-lookup"><span data-stu-id="a8ff2-102">Develop with Q# and Python</span></span>

<span data-ttu-id="a8ff2-103">Installera QDK:n om du vill utveckla Python-värdprogram som anropar Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="a8ff2-104">Installera Python-paketet `qsharp`</span><span class="sxs-lookup"><span data-stu-id="a8ff2-104">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="a8ff2-105">Installera med hjälp av conda (rekommenderas)</span><span class="sxs-lookup"><span data-stu-id="a8ff2-105">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="a8ff2-106">Installera [Miniconda](https://docs.conda.io/en/latest/miniconda.html) eller [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="a8ff2-106">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="a8ff2-107">**Obs!** 64-bitarsinstallation krävs.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-107">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="a8ff2-108">Öppna en Anaconda-prompt.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-108">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="a8ff2-109">Eller om du föredrar att använda PowerShell eller pwsh: öppna ett gränssnitt, kör `conda init powershell`, stäng och öppna sedan gränssnittet igen.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-109">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="a8ff2-110">Skapa och aktivera en ny conda-miljö som heter `qsharp-env` med de nödvändiga paketen (inklusive Jupyter Notebook och IQ#) genom att köra följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="a8ff2-110">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="a8ff2-111">Kör `python -c "import qsharp"` från samma terminal för att verifiera installationen och fylla i det lokala paketets cacheminne med alla nödvändiga QDK-komponenter.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-111">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="a8ff2-112">Installera med hjälp av .NET CLI och pip (avancerat)</span><span class="sxs-lookup"><span data-stu-id="a8ff2-112">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="a8ff2-113">Krav:</span><span class="sxs-lookup"><span data-stu-id="a8ff2-113">Prerequisites:</span></span>

    - <span data-ttu-id="a8ff2-114">[Python](https://www.python.org/downloads/) 3.6 eller senare</span><span class="sxs-lookup"><span data-stu-id="a8ff2-114">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="a8ff2-115">[PIP](https://pip.pypa.io/en/stable/installing) Python-pakethanterare</span><span class="sxs-lookup"><span data-stu-id="a8ff2-115">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="a8ff2-116">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="a8ff2-116">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="a8ff2-117">Installera `qsharp`-paketet, vilket är ett Python-paket som ger interoperabilitet mellan Q# och Python.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-117">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="a8ff2-118">Installera IQ#, vilket är en kernel som främst används av Jupyter och Python och som innehåller grundläggande funktioner för att kompilera och köra Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-118">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="a8ff2-119">Om du får ett felmeddelande under `dotnet iqsharp install`-steget, öppnar du ett nytt terminalfönster och försöker igen.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-119">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="a8ff2-120">Om det fortfarande inte fungerar kan du försöka hitta det installerade `dotnet-iqsharp`-verktyget (i Windows, `dotnet-iqsharp.exe`) och köra:</span><span class="sxs-lookup"><span data-stu-id="a8ff2-120">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="a8ff2-121">där `/path/to/dotnet-iqsharp` ersätts med den absoluta sökvägen till `dotnet-iqsharp`-verktyget i filsystemet.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-121">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="a8ff2-122">Den finns vanligtvis under `.dotnet/tools` i användarprofilens mapp.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-122">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="a8ff2-123">Klart!</span><span class="sxs-lookup"><span data-stu-id="a8ff2-123">That's it!</span></span> <span data-ttu-id="a8ff2-124">Nu har du både Python-paketet `qsharp` och IQ#-kärnan för Jupyter, som tillhandahåller grundläggande funktioner för kompilering och körning av Q#-åtgärder från Python samt ger möjlighet att använda Q# Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-124">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="a8ff2-125">Välja IDE</span><span class="sxs-lookup"><span data-stu-id="a8ff2-125">Choose your IDE</span></span>

<span data-ttu-id="a8ff2-126">Även om du kan använda Q# med Python i en IDE, rekommenderar vi starkt att du använder IDE:n i Visual Studio Code (VS Code) till dina Q# + Python-program.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-126">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="a8ff2-127">Med QDK Visual Studio Code-tillägget får du tillgång till omfattande funktioner såsom varningar, syntaxmarkeringar, projektmallar och mer.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-127">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="a8ff2-128">Om du vill använda VS Code:</span><span class="sxs-lookup"><span data-stu-id="a8ff2-128">If you would like to use VS Code:</span></span>

- <span data-ttu-id="a8ff2-129">Installera [VS Code](https://code.visualstudio.com/download) (Windows, Linux och Mac).</span><span class="sxs-lookup"><span data-stu-id="a8ff2-129">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="a8ff2-130">Installera [QDK-tillägget för VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="a8ff2-130">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="a8ff2-131">Om du vill använda ett annat redigeringsprogram får du hjälp av anvisningarna ovan.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-131">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-q-program"></a><span data-ttu-id="a8ff2-132">Skriva ditt första Q#-program</span><span class="sxs-lookup"><span data-stu-id="a8ff2-132">Write your first Q# program</span></span>

<span data-ttu-id="a8ff2-133">Nu är du redo att verifiera installationen av Python-paketet `qsharp` genom att skriva och köra ett enkelt Q#-program.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-133">Now you are ready to verify your `qsharp` Python package installation by writing and executing a simple Q# program.</span></span>

1. <span data-ttu-id="a8ff2-134">Skapa en minimal Q#-åtgärd genom att skapa en fil med namnet `Operation.qs` och lägga till följande kod i den:</span><span class="sxs-lookup"><span data-stu-id="a8ff2-134">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="a8ff2-135">I samma mapp som `Operation.qs` skapar du ett Python-program som heter `host.py` för att simulera Q#-åtgärden `SampleQuantumRandomNumberGenerator()`:</span><span class="sxs-lookup"><span data-stu-id="a8ff2-135">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    SampleQuantumRandomNumberGenerator.simulate()
    ```

1. <span data-ttu-id="a8ff2-136">Från den miljö som du skapade under installationen (det vill säga den conda- eller Python-miljö där du installerade `qsharp`) kör du programmet:</span><span class="sxs-lookup"><span data-stu-id="a8ff2-136">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="a8ff2-137">Du bör se resultatet av den åtgärd du anropade.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-137">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="a8ff2-138">Eftersom åtgärden genererar ett slumpmässigt resultat visas i det här fallet antingen `Zero` eller `One` på skärmen.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-138">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="a8ff2-139">Om du kör programmet upprepade gånger bör du se varje resultat ungefär varannan gång.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-139">If you execute the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> * <span data-ttu-id="a8ff2-140">Python-koden är bara ett vanligt Python-program.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-140">The Python code is just a normal Python program.</span></span> <span data-ttu-id="a8ff2-141">Du kan använda valfri Python-miljö, däribland Python-baserade Jupyter Notebooks, för att skriva Python-programmet och anropa Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-141">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="a8ff2-142">Python-programmet kan importera Q#-åtgärder från .qs-filer som finns i samma mapp som själva Python-koden.</span><span class="sxs-lookup"><span data-stu-id="a8ff2-142">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8ff2-143">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a8ff2-143">Next steps</span></span>

<span data-ttu-id="a8ff2-144">Nu när du har installerat Quantum Development Kit i önskad miljö kan du gå igenom den här självstudien för att skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="a8ff2-144">Now that you have installed the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
