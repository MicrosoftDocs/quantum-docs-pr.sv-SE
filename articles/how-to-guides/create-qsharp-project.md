---
title: 'Lär dig hur du skapar ett Q #-projekt med Quantum Development Kit (QDK)'
description: 'Initiera ett projekt för en Quantum-utveckling med QDK och Q # i den utvecklings miljö du väljer'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8af8e3288aab731520ede984d5f89644de292385
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578219"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="b8ac4-103">Skapa ett Q #-projekt i utvecklings miljön</span><span class="sxs-lookup"><span data-stu-id="b8ac4-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="b8ac4-104">Lär dig hur du skapar ett Q #-projekt med QDK.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="b8ac4-105">Ett Q #-projekt innehåller Q #-filer som innehåller Quantum-kod, samt ett värd program för att köra programmet Quantum.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="b8ac4-106">Du kan skriva värd programmet i .NET-språk, till exempel C#, eller i python.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="b8ac4-107">Du kan också köra Q # kod i en Jupyter Notebook med SWEETIQ # kernel.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-107">You can also run Q# code in a Jupyter Notebook using the IQ# kernel.</span></span>

<span data-ttu-id="b8ac4-108">Välj utvecklings miljö och språk i avsnitten nedan:</span><span class="sxs-lookup"><span data-stu-id="b8ac4-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="b8ac4-109">Python</span><span class="sxs-lookup"><span data-stu-id="b8ac4-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="b8ac4-110">Q# Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="b8ac4-110">Q# Jupyter Notebooks</span></span>](#create-a-q-jupyter-notebook-project)
* [<span data-ttu-id="b8ac4-111">C# med Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b8ac4-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="b8ac4-112">C# med VS Code</span><span class="sxs-lookup"><span data-stu-id="b8ac4-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="b8ac4-113">C# med kommando raden</span><span class="sxs-lookup"><span data-stu-id="b8ac4-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="b8ac4-114">Skapa ett python-projekt</span><span class="sxs-lookup"><span data-stu-id="b8ac4-114">Create a Python project</span></span>

1. <span data-ttu-id="b8ac4-115">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b8ac4-115">Pre-requisites</span></span>

     * <span data-ttu-id="b8ac4-116">Installera [Quantum Development Kit för python](xref:microsoft.quantum.install.python)</span><span class="sxs-lookup"><span data-stu-id="b8ac4-116">Install the [Quantum Development Kit for Python](xref:microsoft.quantum.install.python)</span></span>

1. <span data-ttu-id="b8ac4-117">Skapa en mapp för ditt projekt och navigera till den mappen</span><span class="sxs-lookup"><span data-stu-id="b8ac4-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="b8ac4-118">Skapa en Q #-fil med namnet `Operation.qs` och Lägg till din q #-kod till den.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="b8ac4-119">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="b8ac4-119">For example:</span></span>

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

1. <span data-ttu-id="b8ac4-120">Skapa en python-värd fil `host.py` som kallas för att anropa din Q #-åtgärd.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="b8ac4-121">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="b8ac4-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="b8ac4-122">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="b8ac4-122">Run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="b8ac4-123">Verifiera utdata.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-123">Verify the output.</span></span> <span data-ttu-id="b8ac4-124">Följande rader ska visas av programmet:</span><span class="sxs-lookup"><span data-stu-id="b8ac4-124">Your program should output the following lines:</span></span>

    ```
    Hello from quantum world!
    0
    ```

<span data-ttu-id="b8ac4-125">Nu kan du fortsätta att utveckla ditt Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-q-jupyter-notebook-project"></a><span data-ttu-id="b8ac4-126">Skapa ett Q # Jupyter Notebook-projekt</span><span class="sxs-lookup"><span data-stu-id="b8ac4-126">Create a Q# Jupyter Notebook project</span></span>

1. <span data-ttu-id="b8ac4-127">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b8ac4-127">Pre-requisites</span></span>

    * <span data-ttu-id="b8ac4-128">Installera [Quantum Development Kit för Jupyter Notebooks](xref:microsoft.quantum.install.jupyter)</span><span class="sxs-lookup"><span data-stu-id="b8ac4-128">Install the [Quantum Development Kit for Jupyter Notebooks](xref:microsoft.quantum.install.jupyter)</span></span>

1. <span data-ttu-id="b8ac4-129">Kör följande kommando för att starta Notebook-servern:</span><span class="sxs-lookup"><span data-stu-id="b8ac4-129">Run the following command to start the notebook server:</span></span>

    ```
    jupyter notebook
    ```

1. <span data-ttu-id="b8ac4-130">Bläddra till den URL som visas på kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="b8ac4-131">Till exempel: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span><span class="sxs-lookup"><span data-stu-id="b8ac4-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="b8ac4-132">En Jupyter-sida visas i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="b8ac4-133">På fliken **filer** väljer du **ny**  >  **Q #** för att skapa en Jupyter Notebook med en Q #-kernel.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter Notebook with a Q# kernel.</span></span> <span data-ttu-id="b8ac4-134">Lägg till följande kod i den första notebook-cellen:</span><span class="sxs-lookup"><span data-stu-id="b8ac4-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="b8ac4-135">Välj **cell**  >  **körnings celler** för att köra antecknings boken.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="b8ac4-136">`SayHello`kommer snart att visas i cellens utdata:</span><span class="sxs-lookup"><span data-stu-id="b8ac4-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Jupyter Notebook cell med Q # Code](~/media/install-guide-jupyter.png)

    <span data-ttu-id="b8ac4-138">När du kör i Jupyter-anteckningsböcker kompileras Q #-koden och antecknings boken visar namnet på den eller de åtgärder som den hittar.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="b8ac4-139">I en ny cell simulerar du körningen i en kvantdator för den åtgärd som du nyss skapade med hjälp av `%simulate`-magic:</span><span class="sxs-lookup"><span data-stu-id="b8ac4-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Jupyter Notebook cell med% simulera Magic](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="b8ac4-141">Du bör se meddelandet på skärmen tillsammans med resultatet av den åtgärd du anropade (i det här fallet är det tomt).</span><span class="sxs-lookup"><span data-stu-id="b8ac4-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="b8ac4-142">Nu kan du lägga till andra Q #-åtgärder för att fortsätta din Quantum-utveckling.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="b8ac4-143">Skapa ett C#-projekt i Windows med Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b8ac4-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="b8ac4-144">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b8ac4-144">Pre-requisites</span></span>

    * <span data-ttu-id="b8ac4-145">Installera [Quantum Development Kit-tillägget för Visual Studio](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="b8ac4-145">Install the [Quantum Development Kit extension for Visual Studio](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="b8ac4-146">Skapa ett nytt Q#-program</span><span class="sxs-lookup"><span data-stu-id="b8ac4-146">Create a new Q# application</span></span>

    * <span data-ttu-id="b8ac4-147">Gå till **filen**  ->  **nytt**  ->  **projekt**</span><span class="sxs-lookup"><span data-stu-id="b8ac4-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="b8ac4-148">Skriv `Q#` i sökrutan</span><span class="sxs-lookup"><span data-stu-id="b8ac4-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="b8ac4-149">Välj **Q#-program**</span><span class="sxs-lookup"><span data-stu-id="b8ac4-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="b8ac4-150">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="b8ac4-150">Select **Next**</span></span>
    * <span data-ttu-id="b8ac4-151">Välj ett namn och en plats för ditt program</span><span class="sxs-lookup"><span data-stu-id="b8ac4-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="b8ac4-152">Välj **skapa**</span><span class="sxs-lookup"><span data-stu-id="b8ac4-152">Select **Create**</span></span>

1. <span data-ttu-id="b8ac4-153">Inspektera projektet</span><span class="sxs-lookup"><span data-stu-id="b8ac4-153">Inspect the project</span></span>

    <span data-ttu-id="b8ac4-154">Du bör se att två filer har skapats: `Driver.cs`, vilket är C#-värdprogrammet och `Operation.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="b8ac4-155">Kör programmet</span><span class="sxs-lookup"><span data-stu-id="b8ac4-155">Run the application</span></span>

    * <span data-ttu-id="b8ac4-156">Välj **fel söknings**  ->  **Start utan fel sökning**</span><span class="sxs-lookup"><span data-stu-id="b8ac4-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="b8ac4-157">Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="b8ac4-158">Nu kan du fortsätta med din Quantum-utveckling med Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b8ac4-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="b8ac4-159">Om du har flera projekt i en Visual Studio-lösning måste alla projekt i lösningen finnas i samma mapp som lösningen, eller i en av dess undermappar.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="b8ac4-160">Skapa ett C#-projekt med VS Code</span><span class="sxs-lookup"><span data-stu-id="b8ac4-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="b8ac4-161">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b8ac4-161">Pre-requisites</span></span>

    * <span data-ttu-id="b8ac4-162">Installera [Quantum Development Kit-tillägget för vs Code](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="b8ac4-162">Install the [Quantum Development Kit extension for VS Code](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="b8ac4-163">Skapa ett nytt projekt:</span><span class="sxs-lookup"><span data-stu-id="b8ac4-163">Create a new project:</span></span>

    * <span data-ttu-id="b8ac4-164">Gå till **Visa**  ->  **kommando palett**</span><span class="sxs-lookup"><span data-stu-id="b8ac4-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="b8ac4-165">Välj **Q #: skapa nytt projekt**</span><span class="sxs-lookup"><span data-stu-id="b8ac4-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="b8ac4-166">Välj **fristående konsol program**</span><span class="sxs-lookup"><span data-stu-id="b8ac4-166">Select **Standalone console application**</span></span>
    * <span data-ttu-id="b8ac4-167">Gå till den plats i filsystemet där du vill skapa programmet</span><span class="sxs-lookup"><span data-stu-id="b8ac4-167">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="b8ac4-168">Klicka på knappen **Öppna nytt projekt...** när projektet har skapats</span><span class="sxs-lookup"><span data-stu-id="b8ac4-168">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="b8ac4-169">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="b8ac4-169">Run the application:</span></span>

    * <span data-ttu-id="b8ac4-170">Gå till **Terminal**,  ->  **ny terminal**</span><span class="sxs-lookup"><span data-stu-id="b8ac4-170">Go to **Terminal** -> **New Terminal**</span></span>
    * <span data-ttu-id="b8ac4-171">Ange `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="b8ac4-171">Enter `dotnet run`</span></span>
    * <span data-ttu-id="b8ac4-172">Du bör se följande text i utdatafönstret `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b8ac4-172">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="b8ac4-173">Nu kan du fortsätta med din Quantum-utveckling med Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-173">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="b8ac4-174">Arbetsytor med flera rotmappar stöds för närvarande inte av Visual Studio Code-tillägget.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-174">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="b8ac4-175">Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-175">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="b8ac4-176">Skapa ett C#-projekt med `dotnet` kommando rads verktyget</span><span class="sxs-lookup"><span data-stu-id="b8ac4-176">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="b8ac4-177">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b8ac4-177">Pre-requisites</span></span>

    * <span data-ttu-id="b8ac4-178">Installera [Quantum Development Kit för kommando raden](xref:microsoft.quantum.install.standalone)</span><span class="sxs-lookup"><span data-stu-id="b8ac4-178">Install the [Quantum Development Kit for the command line](xref:microsoft.quantum.install.standalone)</span></span>

1. <span data-ttu-id="b8ac4-179">Skapa ett nytt program</span><span class="sxs-lookup"><span data-stu-id="b8ac4-179">Create a new application</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="b8ac4-180">Gå till den nya programkatalogen</span><span class="sxs-lookup"><span data-stu-id="b8ac4-180">Navigate to the new application directory</span></span>

    ```
    cd <project name>
    ```

    <span data-ttu-id="b8ac4-181">Du bör se att två filer har skapats, tillsammans med projektfilerna för programmet: en Q#-fil (`Operation.qs`) och en C#-värdfil (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="b8ac4-181">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="b8ac4-182">Kör programmet</span><span class="sxs-lookup"><span data-stu-id="b8ac4-182">Run the application</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="b8ac4-183">Du bör se följande utdata: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b8ac4-183">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="b8ac4-184">Nu kan du fortsätta med en Quantum-utveckling med hjälp av kommando rads verktyg.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-184">You now continue your quantum development, using command line tools.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b8ac4-185">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b8ac4-185">Next steps</span></span>

<span data-ttu-id="b8ac4-186">Nu när du har skapat ett projekt i din önskade miljö kan du fortsätta med en Quantum-utveckling.</span><span class="sxs-lookup"><span data-stu-id="b8ac4-186">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
