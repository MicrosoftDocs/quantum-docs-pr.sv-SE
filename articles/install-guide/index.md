---
title: Lär dig att installera Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035288"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="2e26a-102">Installera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="2e26a-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="2e26a-103">Lär dig att installera Microsoft Quantum Development Kit (QDK) så att du kan komma igång med kvantprogrammering.</span><span class="sxs-lookup"><span data-stu-id="2e26a-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="2e26a-104">QDK består av:</span><span class="sxs-lookup"><span data-stu-id="2e26a-104">The QDK consists of:</span></span>

- <span data-ttu-id="2e26a-105">programmeringsspråket Q#</span><span class="sxs-lookup"><span data-stu-id="2e26a-105">the Q# programming language</span></span>
- <span data-ttu-id="2e26a-106">en uppsättning med bibliotek som abstraherar komplexa funktioner i Q#</span><span class="sxs-lookup"><span data-stu-id="2e26a-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="2e26a-107">ett värdprogram (skrivet i Python eller ett .NET-språk) som kör kvantåtgärder som har skrivits i Q#</span><span class="sxs-lookup"><span data-stu-id="2e26a-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="2e26a-108">verktyg som underlättar ditt utvecklingsarbete</span><span class="sxs-lookup"><span data-stu-id="2e26a-108">tools to facilitate your development</span></span>

<span data-ttu-id="2e26a-109">Beroende på din valda utvecklingsmiljö finns det olika installationssteg.</span><span class="sxs-lookup"><span data-stu-id="2e26a-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="2e26a-110">Välj din miljö i avsnitten nedan.</span><span class="sxs-lookup"><span data-stu-id="2e26a-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="2e26a-111">Utveckla med Python</span><span class="sxs-lookup"><span data-stu-id="2e26a-111">Develop with Python</span></span>

1. <span data-ttu-id="2e26a-112">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="2e26a-112">Pre-requisites</span></span>

    - <span data-ttu-id="2e26a-113">[Python](https://www.python.org/downloads/) 3.6 eller senare</span><span class="sxs-lookup"><span data-stu-id="2e26a-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="2e26a-114">[PIP](https://pip.pypa.io/en/stable/installing) Python-pakethanterare</span><span class="sxs-lookup"><span data-stu-id="2e26a-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="2e26a-115">.NET Core SDK 2.1 eller senare</span><span class="sxs-lookup"><span data-stu-id="2e26a-115">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="2e26a-116">Installera `iqsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="2e26a-116">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="2e26a-117">Installera `qsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="2e26a-117">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="2e26a-118">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="2e26a-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="2e26a-119">Skapa en minimal Q#-åtgärd genom att skapa en fil med namnet `Operation.qs` och lägg till följande kod i den:</span><span class="sxs-lookup"><span data-stu-id="2e26a-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - <span data-ttu-id="2e26a-120">Skapa ett Python-program med namnet `hello_world.py` som anropar åtgärden `SayHello()` Q#:</span><span class="sxs-lookup"><span data-stu-id="2e26a-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="2e26a-121">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="2e26a-121">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="2e26a-122">Verifiera utdata.</span><span class="sxs-lookup"><span data-stu-id="2e26a-122">Verify the output.</span></span> <span data-ttu-id="2e26a-123">Följande rader ska visas av programmet:</span><span class="sxs-lookup"><span data-stu-id="2e26a-123">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="2e26a-124">Utveckla med Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="2e26a-124">Develop with Jupyter notebooks</span></span>

1. <span data-ttu-id="2e26a-125">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="2e26a-125">Pre-requisites</span></span>

    - <span data-ttu-id="2e26a-126">[Python](https://www.python.org/downloads/) 3.6 eller senare</span><span class="sxs-lookup"><span data-stu-id="2e26a-126">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="2e26a-127">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="2e26a-127">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="2e26a-128">.NET Core SDK 2.1 eller senare</span><span class="sxs-lookup"><span data-stu-id="2e26a-128">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="2e26a-129">Installera `iqsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="2e26a-129">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="2e26a-130">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="2e26a-130">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="2e26a-131">Kör följande kommando för att starta Notebook-servern:</span><span class="sxs-lookup"><span data-stu-id="2e26a-131">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="2e26a-132">Bläddra till den URL som visas på kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="2e26a-132">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="2e26a-133">Till exempel: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="2e26a-133">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="2e26a-134">Skapa en Jupyter Notebook med en Q#-kernel och lägg till följande kod i den första Notebook-cellen:</span><span class="sxs-lookup"><span data-stu-id="2e26a-134">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="2e26a-135">Kör följande Notebook-cell:</span><span class="sxs-lookup"><span data-stu-id="2e26a-135">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook-cell](~/media/install-guide-jupyter.png)

        <span data-ttu-id="2e26a-137">Du bör se `SayHello` i cellens utdata.</span><span class="sxs-lookup"><span data-stu-id="2e26a-137">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="2e26a-138">När du använder Jupyter Notebook kompileras Q#-koden och Notebook visar namnet på den eller de åtgärder som den hittar.</span><span class="sxs-lookup"><span data-stu-id="2e26a-138">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="2e26a-139">Utveckla med C# i Windows med Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e26a-139">Develop with C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="2e26a-140">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="2e26a-140">Pre-requisites</span></span>

    - <span data-ttu-id="2e26a-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat</span><span class="sxs-lookup"><span data-stu-id="2e26a-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="2e26a-142">Installera Q# Visual Studio-tillägget</span><span class="sxs-lookup"><span data-stu-id="2e26a-142">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="2e26a-143">Ladda ned [Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="2e26a-143">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="2e26a-144">Lägg till tillägget i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e26a-144">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="2e26a-145">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="2e26a-145">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="2e26a-146">Skapa ett nytt Q#-program</span><span class="sxs-lookup"><span data-stu-id="2e26a-146">Create a new Q# application</span></span>

        - <span data-ttu-id="2e26a-147">Gå till **Arkiv** -> **Nytt** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="2e26a-147">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="2e26a-148">Skriv `Q#` i sökrutan</span><span class="sxs-lookup"><span data-stu-id="2e26a-148">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="2e26a-149">Välj **Q#-program**</span><span class="sxs-lookup"><span data-stu-id="2e26a-149">Select **Q# Application**</span></span>
        - <span data-ttu-id="2e26a-150">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="2e26a-150">Select **Next**</span></span>
        - <span data-ttu-id="2e26a-151">Välj ett namn och en plats för ditt program</span><span class="sxs-lookup"><span data-stu-id="2e26a-151">Choose a name and location for your application</span></span>
        - <span data-ttu-id="2e26a-152">Välj **Skapa**</span><span class="sxs-lookup"><span data-stu-id="2e26a-152">Select **Create**</span></span>

    - <span data-ttu-id="2e26a-153">Inspektera projektet</span><span class="sxs-lookup"><span data-stu-id="2e26a-153">Inspect the project</span></span>

        <span data-ttu-id="2e26a-154">Du bör se att två filer har skapats: `Driver.cs`, vilket är C#-värdprogrammet och `Operation.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="2e26a-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="2e26a-155">Köra programmet</span><span class="sxs-lookup"><span data-stu-id="2e26a-155">Run the application</span></span>

        - <span data-ttu-id="2e26a-156">Välj **Felsökning** -> **Starta utan felsökning**</span><span class="sxs-lookup"><span data-stu-id="2e26a-156">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="2e26a-157">Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.</span><span class="sxs-lookup"><span data-stu-id="2e26a-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="2e26a-158">Om du har flera projekt i en Visual Studio-lösning måste alla projekt i lösningen finnas i samma mapp som lösningen, eller i en av dess undermappar.</span><span class="sxs-lookup"><span data-stu-id="2e26a-158">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-vs-code"></a><span data-ttu-id="2e26a-159">Utveckla i C# med VS Code</span><span class="sxs-lookup"><span data-stu-id="2e26a-159">Develop with C#, using VS Code</span></span>

1. <span data-ttu-id="2e26a-160">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="2e26a-160">Pre-requisites</span></span>

   - [<span data-ttu-id="2e26a-161">VS-kod</span><span class="sxs-lookup"><span data-stu-id="2e26a-161">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="2e26a-162">.NET Core SDK 2.1 eller senare</span><span class="sxs-lookup"><span data-stu-id="2e26a-162">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="2e26a-163">Installera Quantum VS Code-tillägget</span><span class="sxs-lookup"><span data-stu-id="2e26a-163">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="2e26a-164">Installera [VS Code-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="2e26a-164">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="2e26a-165">Installera Quantum-projektmallarna:</span><span class="sxs-lookup"><span data-stu-id="2e26a-165">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="2e26a-166">Gå till **Visa** -> **Kommandopaletten**</span><span class="sxs-lookup"><span data-stu-id="2e26a-166">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="2e26a-167">Välj **Q#: Installera projektmallar**</span><span class="sxs-lookup"><span data-stu-id="2e26a-167">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="2e26a-168">Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.</span><span class="sxs-lookup"><span data-stu-id="2e26a-168">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="2e26a-169">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="2e26a-169">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="2e26a-170">Skapa ett nytt projekt:</span><span class="sxs-lookup"><span data-stu-id="2e26a-170">Create a new project:</span></span>

        - <span data-ttu-id="2e26a-171">Gå till **Visa** -> **Kommandopaletten**</span><span class="sxs-lookup"><span data-stu-id="2e26a-171">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="2e26a-172">Välj **Q#: Skapa nytt projekt**</span><span class="sxs-lookup"><span data-stu-id="2e26a-172">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="2e26a-173">Gå till den plats i filsystemet där du vill skapa programmet</span><span class="sxs-lookup"><span data-stu-id="2e26a-173">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="2e26a-174">Klicka på knappen **Öppna nytt projekt...** när projektet har skapats</span><span class="sxs-lookup"><span data-stu-id="2e26a-174">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="2e26a-175">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="2e26a-175">Run the application:</span></span>

        - <span data-ttu-id="2e26a-176">Gå till **Felsökning** -> **Starta utan felsökning**</span><span class="sxs-lookup"><span data-stu-id="2e26a-176">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="2e26a-177">Du bör se följande text i utdatafönstret `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="2e26a-177">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="2e26a-178">Arbetsytor med flera rotmappar stöds för närvarande inte av Visual Studio Code-tillägget.</span><span class="sxs-lookup"><span data-stu-id="2e26a-178">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="2e26a-179">Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.</span><span class="sxs-lookup"><span data-stu-id="2e26a-179">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="2e26a-180">Utveckla med C# med hjälp av kommandoradsverktyget `dotnet`</span><span class="sxs-lookup"><span data-stu-id="2e26a-180">Develop with C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="2e26a-181">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="2e26a-181">Pre-requisites</span></span>

    - [<span data-ttu-id="2e26a-182">.NET Core SDK 2.1 eller senare</span><span class="sxs-lookup"><span data-stu-id="2e26a-182">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="2e26a-183">Installera kvantprojektmallar för .NET</span><span class="sxs-lookup"><span data-stu-id="2e26a-183">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="2e26a-184">Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.</span><span class="sxs-lookup"><span data-stu-id="2e26a-184">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="2e26a-185">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="2e26a-185">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="2e26a-186">Skapa ett nytt program</span><span class="sxs-lookup"><span data-stu-id="2e26a-186">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="2e26a-187">Gå till den nya programkatalogen</span><span class="sxs-lookup"><span data-stu-id="2e26a-187">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="2e26a-188">Du bör se att två filer har skapats, tillsammans med projektfilerna för programmet: en Q#-fil (`Operation.qs`) och en C#-värdfil (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="2e26a-188">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="2e26a-189">Köra programmet</span><span class="sxs-lookup"><span data-stu-id="2e26a-189">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="2e26a-190">Du bör se följande utdata: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="2e26a-190">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="2e26a-191">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2e26a-191">What's next?</span></span>

<span data-ttu-id="2e26a-192">Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="2e26a-192">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
