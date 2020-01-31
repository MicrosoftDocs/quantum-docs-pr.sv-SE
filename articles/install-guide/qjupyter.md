---
title: 'Utveckla med Q # Jupyter-anteckningsböcker'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831077"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="f65cc-102">Utveckla med Q # Jupyter-anteckningsböcker</span><span class="sxs-lookup"><span data-stu-id="f65cc-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="f65cc-103">Installera QDK för utveckling av Q #-åtgärder på Q # Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="f65cc-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="f65cc-104">Jupyter Notebooks möjliggör kod körning på plats tillsammans med instruktioner, kommentarer och annat innehåll.</span><span class="sxs-lookup"><span data-stu-id="f65cc-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="f65cc-105">Den här miljön är idealisk för att skriva Q # Code med inbäddade förklaringar eller interaktiva självstudier.</span><span class="sxs-lookup"><span data-stu-id="f65cc-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="f65cc-106">Du måste göra följande för att kunna börja skapa dina egna Q#-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="f65cc-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="f65cc-107">IQ# (uttalas i-q-sharp) är ett tillägg som främst används av Jupyter och Python i .NET Core SDK, och som ger grundläggande funktioner för att kompilera och simulera Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="f65cc-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="f65cc-108">I Q # Jupyter Notebooks kan du bara köra Q # Code, och åtgärderna kan inte anropas från externa värd program (t. ex. C# python eller filer).</span><span class="sxs-lookup"><span data-stu-id="f65cc-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="f65cc-109">Den här miljön är inte lämplig om målet är att kombinera ett externt klassiskt värd program med Quantum-programmet.</span><span class="sxs-lookup"><span data-stu-id="f65cc-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="f65cc-110">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="f65cc-110">Pre-requisites</span></span>

    - <span data-ttu-id="f65cc-111">[Python](https://www.python.org/downloads/) 3.6 eller senare</span><span class="sxs-lookup"><span data-stu-id="f65cc-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="f65cc-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="f65cc-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="f65cc-113">.NET Core SDK 3,1 eller senare</span><span class="sxs-lookup"><span data-stu-id="f65cc-113">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="f65cc-114">Installera `iqsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="f65cc-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="f65cc-115">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="f65cc-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="f65cc-116">Kör följande kommando för att starta Notebook-servern:</span><span class="sxs-lookup"><span data-stu-id="f65cc-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="f65cc-117">Öppna Jupyter Notebook-kopian och klistra in den URL som tillhandahålls av kommando raden i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="f65cc-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="f65cc-118">Skapa en Jupyter Notebook med en Q#-kernel och lägg till följande kod i den första Notebook-cellen:</span><span class="sxs-lookup"><span data-stu-id="f65cc-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="f65cc-119">Kör följande Notebook-cell:</span><span class="sxs-lookup"><span data-stu-id="f65cc-119">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook-cell med Q#-kod](~/media/install-guide-jupyter.png)

        <span data-ttu-id="f65cc-121">Du bör se `SayHello` i cellens utdata.</span><span class="sxs-lookup"><span data-stu-id="f65cc-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="f65cc-122">När du använder Jupyter Notebook kompileras Q#-koden och Notebook visar namnet på den eller de åtgärder som den hittar.</span><span class="sxs-lookup"><span data-stu-id="f65cc-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="f65cc-123">I en ny cell kör du den åtgärd som du nyss skapade (i en simulator) genom att använda kommandot `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="f65cc-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Jupyter Notebook-cell med %simulate magic](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="f65cc-125">Du bör se meddelandet som skrivs ut på skärmen tillsammans med resultatet av den åtgärd du anropade (här visas den tomma tuppeln `()` eftersom vår åtgärd bara returnerar en `Unit` typ).</span><span class="sxs-lookup"><span data-stu-id="f65cc-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="whats-next"></a><span data-ttu-id="f65cc-126">Vad står på tur?</span><span class="sxs-lookup"><span data-stu-id="f65cc-126">What's next?</span></span>

<span data-ttu-id="f65cc-127">Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="f65cc-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
