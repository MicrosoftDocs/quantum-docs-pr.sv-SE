---
title: 'Lär dig hur du skapar ett Q #-projekt med Quantum Development Kit (QDK)'
description: 'Initiera ett projekt för en Quantum-utveckling med QDK och Q # i den utvecklings miljö du väljer'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: b4bec5e7a174b7e2d588331dd2093c7b23a728b0
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444182"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="088a3-103">Skapa ett Q #-projekt i utvecklings miljön</span><span class="sxs-lookup"><span data-stu-id="088a3-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="088a3-104">Lär dig hur du skapar ett Q #-projekt med QDK.</span><span class="sxs-lookup"><span data-stu-id="088a3-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="088a3-105">Ett Q #-projekt innehåller Q #-filer som innehåller Quantum-kod, samt ett värd program för att köra programmet Quantum.</span><span class="sxs-lookup"><span data-stu-id="088a3-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="088a3-106">Du kan skriva värd programmet i .NET-språk som C#, eller i python.</span><span class="sxs-lookup"><span data-stu-id="088a3-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="088a3-107">Du kan också köra Q # Code i en Jupyter-anteckningsbok med SWEETIQ # kernel.</span><span class="sxs-lookup"><span data-stu-id="088a3-107">You can also run Q# code in a Jupyter notebook using the IQ# kernel.</span></span>

<span data-ttu-id="088a3-108">Välj utvecklings miljö och språk i avsnitten nedan:</span><span class="sxs-lookup"><span data-stu-id="088a3-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="088a3-109">Python</span><span class="sxs-lookup"><span data-stu-id="088a3-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="088a3-110">Jupyter-anteckningsböcker</span><span class="sxs-lookup"><span data-stu-id="088a3-110">Jupyter notebooks</span></span>](#create-a-jupyter-notebook-project)
* [<span data-ttu-id="088a3-111">C#med Visual Studio</span><span class="sxs-lookup"><span data-stu-id="088a3-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="088a3-112">C#med VS Code</span><span class="sxs-lookup"><span data-stu-id="088a3-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="088a3-113">C#med kommando raden</span><span class="sxs-lookup"><span data-stu-id="088a3-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="088a3-114">Skapa ett python-projekt</span><span class="sxs-lookup"><span data-stu-id="088a3-114">Create a Python project</span></span>

1. <span data-ttu-id="088a3-115">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="088a3-115">Pre-requisites</span></span>

     * <span data-ttu-id="088a3-116">[Quantum Development Kit för python](xref:microsoft.quantum.install#develop-with-python)</span><span class="sxs-lookup"><span data-stu-id="088a3-116">The [Quantum Development Kit for Python](xref:microsoft.quantum.install#develop-with-python)</span></span>

1. <span data-ttu-id="088a3-117">Skapa en mapp för ditt projekt och navigera till den mappen</span><span class="sxs-lookup"><span data-stu-id="088a3-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="088a3-118">Skapa en f #-fil med namnet `Operation.qs`och Lägg till din Q #-kod.</span><span class="sxs-lookup"><span data-stu-id="088a3-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="088a3-119">Exempel:</span><span class="sxs-lookup"><span data-stu-id="088a3-119">For example:</span></span>

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. <span data-ttu-id="088a3-120">Skapa en python-värd fil med namnet `host.py` för att anropa din Q #-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="088a3-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="088a3-121">Exempel:</span><span class="sxs-lookup"><span data-stu-id="088a3-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="088a3-122">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="088a3-122">Run the program:</span></span>

    ```bash
    python host.py
    ```

1. <span data-ttu-id="088a3-123">Verifiera utdata.</span><span class="sxs-lookup"><span data-stu-id="088a3-123">Verify the output.</span></span> <span data-ttu-id="088a3-124">Följande rader ska visas av programmet:</span><span class="sxs-lookup"><span data-stu-id="088a3-124">Your program should output the following lines:</span></span>

    ```bash
    Hello from quantum world!
    0
    ```

<span data-ttu-id="088a3-125">Nu kan du fortsätta att utveckla ditt Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="088a3-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-jupyter-notebook-project"></a><span data-ttu-id="088a3-126">Skapa ett Jupyter Notebook-projekt</span><span class="sxs-lookup"><span data-stu-id="088a3-126">Create a Jupyter Notebook project</span></span>

1. <span data-ttu-id="088a3-127">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="088a3-127">Pre-requisites</span></span>

    * <span data-ttu-id="088a3-128">[Quantum Development Kit för Jupyter Notebooks](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)</span><span class="sxs-lookup"><span data-stu-id="088a3-128">The [Quantum Development Kit for Jupyter notebooks](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)</span></span>

1. <span data-ttu-id="088a3-129">Kör följande kommando för att starta Notebook-servern:</span><span class="sxs-lookup"><span data-stu-id="088a3-129">Run the following command to start the notebook server:</span></span>

    ```bash
    jupyter notebook
    ```

1. <span data-ttu-id="088a3-130">Bläddra till den URL som visas på kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="088a3-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="088a3-131">Till exempel: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="088a3-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="088a3-132">En Jupyter-sida visas i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="088a3-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="088a3-133">På fliken **filer** väljer du **nytt** > **Q #** för att skapa en Jupyter-anteckningsbok med en Q # kernel.</span><span class="sxs-lookup"><span data-stu-id="088a3-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter notebook with a Q# kernel.</span></span> <span data-ttu-id="088a3-134">Lägg till följande kod i den första notebook-cellen:</span><span class="sxs-lookup"><span data-stu-id="088a3-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="088a3-135">Markera **Cell** > **köra celler** för att köra antecknings boken.</span><span class="sxs-lookup"><span data-stu-id="088a3-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="088a3-136">`SayHello` kommer snart att visas i cellens utdata:</span><span class="sxs-lookup"><span data-stu-id="088a3-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Jupyter Notebook-cell med Q # Code](~/media/install-guide-jupyter.png)

    <span data-ttu-id="088a3-138">När du kör i Jupyter-anteckningsböcker kompileras Q #-koden och antecknings boken visar namnet på den eller de åtgärder som den hittar.</span><span class="sxs-lookup"><span data-stu-id="088a3-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="088a3-139">I en ny cell simulerar du körningen i en Quantum-dator för den åtgärd som du nyss skapade med hjälp av `%simulate` Magic:</span><span class="sxs-lookup"><span data-stu-id="088a3-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Jupyter Notebook-cell med% simulera Magic](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="088a3-141">Du bör se meddelandet som skrivs ut på skärmen tillsammans med resultatet av den åtgärd du anropade (i det här fallet tomt).</span><span class="sxs-lookup"><span data-stu-id="088a3-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="088a3-142">Nu kan du lägga till andra Q #-åtgärder för att fortsätta din Quantum-utveckling.</span><span class="sxs-lookup"><span data-stu-id="088a3-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="088a3-143">Skapa ett C# projekt i Windows med Visual Studio</span><span class="sxs-lookup"><span data-stu-id="088a3-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="088a3-144">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="088a3-144">Pre-requisites</span></span>

    * <span data-ttu-id="088a3-145">[Quantum Development Kit för Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)</span><span class="sxs-lookup"><span data-stu-id="088a3-145">The [Quantum Development Kit for Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)</span></span>

1. <span data-ttu-id="088a3-146">Skapa ett nytt Q#-program</span><span class="sxs-lookup"><span data-stu-id="088a3-146">Create a new Q# application</span></span>

    * <span data-ttu-id="088a3-147">Gå till **Arkiv** -> **Nytt** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="088a3-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="088a3-148">Skriv `Q#` i sökrutan</span><span class="sxs-lookup"><span data-stu-id="088a3-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="088a3-149">Välj **Q#-program**</span><span class="sxs-lookup"><span data-stu-id="088a3-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="088a3-150">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="088a3-150">Select **Next**</span></span>
    * <span data-ttu-id="088a3-151">Välj ett namn och en plats för ditt program</span><span class="sxs-lookup"><span data-stu-id="088a3-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="088a3-152">Välj **Skapa**</span><span class="sxs-lookup"><span data-stu-id="088a3-152">Select **Create**</span></span>

1. <span data-ttu-id="088a3-153">Inspektera projektet</span><span class="sxs-lookup"><span data-stu-id="088a3-153">Inspect the project</span></span>

    <span data-ttu-id="088a3-154">Du bör se att två filer har skapats: `Driver.cs`, vilket är C#-värdprogrammet och `Operation.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="088a3-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="088a3-155">Köra programmet</span><span class="sxs-lookup"><span data-stu-id="088a3-155">Run the application</span></span>

    * <span data-ttu-id="088a3-156">Välj **Felsökning** -> **Starta utan felsökning**</span><span class="sxs-lookup"><span data-stu-id="088a3-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="088a3-157">Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.</span><span class="sxs-lookup"><span data-stu-id="088a3-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="088a3-158">Nu kan du fortsätta med din Quantum-utveckling med Visual Studio</span><span class="sxs-lookup"><span data-stu-id="088a3-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="088a3-159">Om du har flera projekt i en Visual Studio-lösning måste alla projekt i lösningen finnas i samma mapp som lösningen, eller i en av dess undermappar.</span><span class="sxs-lookup"><span data-stu-id="088a3-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="088a3-160">Skapa ett C# projekt med vs Code</span><span class="sxs-lookup"><span data-stu-id="088a3-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="088a3-161">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="088a3-161">Pre-requisites</span></span>

    * <span data-ttu-id="088a3-162">[Quantum Development Kit för vs Code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)</span><span class="sxs-lookup"><span data-stu-id="088a3-162">The [Quantum Development Kit for VS Code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)</span></span>

1. <span data-ttu-id="088a3-163">Skapa ett nytt projekt:</span><span class="sxs-lookup"><span data-stu-id="088a3-163">Create a new project:</span></span>

    * <span data-ttu-id="088a3-164">Gå till **Visa** -> **Kommandopaletten**</span><span class="sxs-lookup"><span data-stu-id="088a3-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="088a3-165">Välj **Q #: skapa nytt projekt**</span><span class="sxs-lookup"><span data-stu-id="088a3-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="088a3-166">Gå till den plats i filsystemet där du vill skapa programmet</span><span class="sxs-lookup"><span data-stu-id="088a3-166">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="088a3-167">Klicka på knappen **Öppna nytt projekt...** när projektet har skapats</span><span class="sxs-lookup"><span data-stu-id="088a3-167">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="088a3-168">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="088a3-168">Run the application:</span></span>

    * <span data-ttu-id="088a3-169">Gå till **Felsökning** -> **Starta utan felsökning**</span><span class="sxs-lookup"><span data-stu-id="088a3-169">Go to **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="088a3-170">Du bör se följande text i utdatafönstret `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="088a3-170">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="088a3-171">Nu kan du fortsätta med din Quantum-utveckling med Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="088a3-171">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="088a3-172">Arbetsytor med flera rotmappar stöds för närvarande inte av Visual Studio Code-tillägget.</span><span class="sxs-lookup"><span data-stu-id="088a3-172">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="088a3-173">Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.</span><span class="sxs-lookup"><span data-stu-id="088a3-173">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="088a3-174">Skapa ett C# projekt med hjälp av kommando rads verktyget `dotnet`</span><span class="sxs-lookup"><span data-stu-id="088a3-174">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="088a3-175">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="088a3-175">Pre-requisites</span></span>

    * <span data-ttu-id="088a3-176">[Quantum Development Kit för kommando raden](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)</span><span class="sxs-lookup"><span data-stu-id="088a3-176">The [Quantum Development Kit for the Command Line](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)</span></span>

1. <span data-ttu-id="088a3-177">Skapa ett nytt program</span><span class="sxs-lookup"><span data-stu-id="088a3-177">Create a new application</span></span>

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="088a3-178">Gå till den nya programkatalogen</span><span class="sxs-lookup"><span data-stu-id="088a3-178">Navigate to the new application directory</span></span>

    ```bash
    cd <project name>
    ```

    <span data-ttu-id="088a3-179">Du bör se att två filer har skapats, tillsammans med projektfilerna för programmet: en Q#-fil (`Operation.qs`) och en C#-värdfil (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="088a3-179">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="088a3-180">Köra programmet</span><span class="sxs-lookup"><span data-stu-id="088a3-180">Run the application</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="088a3-181">Du bör se följande utdata: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="088a3-181">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="088a3-182">Nu kan du fortsätta med en Quantum-utveckling med hjälp av kommando rads verktyg.</span><span class="sxs-lookup"><span data-stu-id="088a3-182">You now continue your quantum development, using command line tools.</span></span>

## <a name="whats-next"></a><span data-ttu-id="088a3-183">Vad står på tur?</span><span class="sxs-lookup"><span data-stu-id="088a3-183">What's next?</span></span>

<span data-ttu-id="088a3-184">Nu när du har skapat ett projekt i din önskade miljö kan du fortsätta med en Quantum-utveckling.</span><span class="sxs-lookup"><span data-stu-id="088a3-184">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
