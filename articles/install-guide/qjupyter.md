---
title: Utveckla med Q# Jupyter Notebooks
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b80d95a160b5f46c1132d3428ba32ad6dcd5656e
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630336"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="bdf05-102">Utveckla med Q# Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="bdf05-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="bdf05-103">Installera QDK för utveckling av Q #-åtgärder på Q # Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="bdf05-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="bdf05-104">Jupyter Notebooks möjliggör kod körning på plats tillsammans med instruktioner, kommentarer och annat innehåll.</span><span class="sxs-lookup"><span data-stu-id="bdf05-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="bdf05-105">Den här miljön är idealisk för att skriva Q # Code med inbäddade förklaringar eller interaktiva självstudier.</span><span class="sxs-lookup"><span data-stu-id="bdf05-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="bdf05-106">Du måste göra följande för att kunna börja skapa dina egna Q#-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="bdf05-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="bdf05-107">IQ# (uttalas i-q-sharp) är ett tillägg som främst används av Jupyter och Python i .NET Core SDK, och som ger grundläggande funktioner för att kompilera och simulera Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="bdf05-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="bdf05-108">I Q # Jupyter Notebooks kan du bara köra Q # Code, och åtgärderna kan inte anropas från externa värd program (t. ex. python-eller C#-filer).</span><span class="sxs-lookup"><span data-stu-id="bdf05-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="bdf05-109">Den här miljön är inte lämplig om målet är att kombinera ett externt klassiskt värd program med Quantum-programmet.</span><span class="sxs-lookup"><span data-stu-id="bdf05-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="bdf05-110">Krav</span><span class="sxs-lookup"><span data-stu-id="bdf05-110">Prerequisites</span></span>

    - <span data-ttu-id="bdf05-111">[Python](https://www.python.org/downloads/) 3.6 eller senare</span><span class="sxs-lookup"><span data-stu-id="bdf05-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="bdf05-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="bdf05-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="bdf05-113">.NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="bdf05-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="bdf05-114">Installera `iqsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="bdf05-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="bdf05-115">Om du får ett fel under `dotnet iqsharp install` steget öppnar du ett nytt terminalfönster och försöker igen.</span><span class="sxs-lookup"><span data-stu-id="bdf05-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="bdf05-116">Om det fortfarande inte fungerar kan du försöka hitta det installerade `dotnet-iqsharp` verktyget (i Windows `dotnet-iqsharp.exe` ) och köra:</span><span class="sxs-lookup"><span data-stu-id="bdf05-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="bdf05-117">var `/path/to/dotnet-iqsharp` bör ersättas av den absoluta sökvägen till `dotnet-iqsharp` verktyget i fil systemet.</span><span class="sxs-lookup"><span data-stu-id="bdf05-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="bdf05-118">Detta är vanligt vis under `.dotnet/tools` i mappen användar profil.</span><span class="sxs-lookup"><span data-stu-id="bdf05-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="bdf05-119">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="bdf05-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="bdf05-120">Kör följande kommando för att starta Notebook-servern:</span><span class="sxs-lookup"><span data-stu-id="bdf05-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="bdf05-121">Om du vill öppna Jupyter Notebook kopierar du och klistrar in webb adressen som tillhandahålls av kommando raden i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="bdf05-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="bdf05-122">Skapa en Jupyter Notebook med en Q #-kernel och Lägg till följande kod i den första notebook-cellen:</span><span class="sxs-lookup"><span data-stu-id="bdf05-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="bdf05-123">Kör följande Notebook-cell:</span><span class="sxs-lookup"><span data-stu-id="bdf05-123">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook cell med Q # Code](~/media/install-guide-jupyter.png)

        <span data-ttu-id="bdf05-125">Du bör se `SayHello` i cellens utdata.</span><span class="sxs-lookup"><span data-stu-id="bdf05-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="bdf05-126">När du kör i Jupyter Notebook kompileras Q #-koden och antecknings boken visar namnet på den eller de åtgärder som den hittar.</span><span class="sxs-lookup"><span data-stu-id="bdf05-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="bdf05-127">I en ny cell kör du åtgärden som du nyss skapade (i en simulator) genom att använda `%simulate` kommandot:</span><span class="sxs-lookup"><span data-stu-id="bdf05-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Jupyter Notebook cell med% simulera Magic](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="bdf05-129">Du bör se meddelandet som skrivs ut på skärmen tillsammans med resultatet av den åtgärd du anropade (här ser vi den tomma tuppeln `()` eftersom vår åtgärd bara returnerar en `Unit` typ).</span><span class="sxs-lookup"><span data-stu-id="bdf05-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="bdf05-130">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="bdf05-130">Next steps</span></span>

<span data-ttu-id="bdf05-131">Nu när du har installerat QDK för Q # Jupyter Notebooks kan du skriva och köra [ditt första Quantum-program](xref:microsoft.quantum.quickstarts.qrng) genom att skriva din Q #-kod direkt i Jupyter Notebooks miljön.</span><span class="sxs-lookup"><span data-stu-id="bdf05-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="bdf05-132">För fler exempel på vad du kan göra med Q # Jupyter notebooks, kan du ta en titt på:</span><span class="sxs-lookup"><span data-stu-id="bdf05-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="bdf05-133">[Introduktion till Q # och Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="bdf05-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="bdf05-134">Där hittar du ett Q #-Jupyter Notebook som visar hur du använder Q # i den här miljön.</span><span class="sxs-lookup"><span data-stu-id="bdf05-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="bdf05-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), en samling med öppen källkod i självstudier och uppsättningar av programmerings övningar i form av Q # Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="bdf05-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="bdf05-136">[Datorerna i Quantum Katas-självstudier](https://github.com/microsoft/QuantumKatas#tutorial-topics) är en start punkt.</span><span class="sxs-lookup"><span data-stu-id="bdf05-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="bdf05-137">Quantum Katas syftar till att lära dig element i Quantum data behandling och Q #-programmering på samma tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="bdf05-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="bdf05-138">De är ett utmärkt exempel på vilken typ av innehåll som du kan skapa med Q # Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="bdf05-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
