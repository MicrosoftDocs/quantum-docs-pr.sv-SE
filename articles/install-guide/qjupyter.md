---
title: Utveckla med Q# Jupyter Notebooks
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 0c4dc856c94b0a694fb99607eda64cec4d5c221d
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660765"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="b5d31-102">Utveckla med Q# Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="b5d31-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="b5d31-103">Installera QDK för utveckling av Q #-åtgärder på Q # Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="b5d31-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="b5d31-104">Jupyter Notebooks möjliggör kod körning på plats tillsammans med instruktioner, kommentarer och annat innehåll.</span><span class="sxs-lookup"><span data-stu-id="b5d31-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="b5d31-105">Den här miljön är idealisk för att skriva Q # Code med inbäddade förklaringar eller interaktiva självstudier.</span><span class="sxs-lookup"><span data-stu-id="b5d31-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="b5d31-106">Du måste göra följande för att kunna börja skapa dina egna Q#-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="b5d31-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="b5d31-107">IQ# (uttalas i-q-sharp) är ett tillägg som främst används av Jupyter och Python i .NET Core SDK, och som ger grundläggande funktioner för att kompilera och simulera Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="b5d31-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="b5d31-108">I Q # Jupyter Notebooks kan du bara köra Q # Code, och åtgärderna kan inte anropas från externa värd program (t. ex. python-eller C#-filer).</span><span class="sxs-lookup"><span data-stu-id="b5d31-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="b5d31-109">Den här miljön är inte lämplig om målet är att kombinera ett externt klassiskt värd program med Quantum-programmet.</span><span class="sxs-lookup"><span data-stu-id="b5d31-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="b5d31-110">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b5d31-110">Pre-requisites</span></span>

    - <span data-ttu-id="b5d31-111">[Python](https://www.python.org/downloads/) 3.6 eller senare</span><span class="sxs-lookup"><span data-stu-id="b5d31-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="b5d31-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="b5d31-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="b5d31-113">.NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="b5d31-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="b5d31-114">Installera `iqsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="b5d31-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="b5d31-115">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="b5d31-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b5d31-116">Kör följande kommando för att starta Notebook-servern:</span><span class="sxs-lookup"><span data-stu-id="b5d31-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="b5d31-117">Om du vill öppna Jupyter Notebook kopierar du och klistrar in webb adressen som tillhandahålls av kommando raden i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="b5d31-117">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="b5d31-118">Skapa en Jupyter Notebook med en Q #-kernel och Lägg till följande kod i den första notebook-cellen:</span><span class="sxs-lookup"><span data-stu-id="b5d31-118">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="b5d31-119">Kör följande Notebook-cell:</span><span class="sxs-lookup"><span data-stu-id="b5d31-119">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook cell med Q # Code](~/media/install-guide-jupyter.png)

        <span data-ttu-id="b5d31-121">Du bör se `SayHello` i cellens utdata.</span><span class="sxs-lookup"><span data-stu-id="b5d31-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="b5d31-122">När du kör i Jupyter Notebook kompileras Q #-koden och antecknings boken visar namnet på den eller de åtgärder som den hittar.</span><span class="sxs-lookup"><span data-stu-id="b5d31-122">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="b5d31-123">I en ny cell kör du åtgärden som du nyss skapade (i en simulator) genom att använda `%simulate` kommandot:</span><span class="sxs-lookup"><span data-stu-id="b5d31-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Jupyter Notebook cell med% simulera Magic](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="b5d31-125">Du bör se meddelandet som skrivs ut på skärmen tillsammans med resultatet av den åtgärd du anropade (här ser vi den tomma tuppeln `()` eftersom vår åtgärd bara returnerar en `Unit` typ).</span><span class="sxs-lookup"><span data-stu-id="b5d31-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b5d31-126">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b5d31-126">Next steps</span></span>

<span data-ttu-id="b5d31-127">Nu när du har installerat QDK för Q # Jupyter Notebooks kan du skriva och köra [ditt första Quantum-program](xref:microsoft.quantum.quickstarts.qrng) genom att skriva din Q #-kod direkt i Jupyter Notebooks miljön.</span><span class="sxs-lookup"><span data-stu-id="b5d31-127">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="b5d31-128">För fler exempel på vad du kan göra med Q # Jupyter notebooks, kan du ta en titt på:</span><span class="sxs-lookup"><span data-stu-id="b5d31-128">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="b5d31-129">[Introduktion till Q # och Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="b5d31-129">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="b5d31-130">Där hittar du ett Q #-Jupyter Notebook som visar hur du använder Q # i den här miljön.</span><span class="sxs-lookup"><span data-stu-id="b5d31-130">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="b5d31-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), en samling med öppen källkod i självstudier och uppsättningar av programmerings övningar i form av Q # Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="b5d31-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="b5d31-132">[Datorerna i Quantum Katas-självstudier](https://github.com/microsoft/QuantumKatas#tutorial-topics) är en start punkt.</span><span class="sxs-lookup"><span data-stu-id="b5d31-132">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="b5d31-133">Quantum Katas syftar till att lära dig element i Quantum data behandling och Q #-programmering på samma tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="b5d31-133">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="b5d31-134">De är ett utmärkt exempel på vilken typ av innehåll som du kan skapa med Q # Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="b5d31-134">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
