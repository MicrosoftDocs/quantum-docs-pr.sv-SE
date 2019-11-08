---
title: Lär dig att installera Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 580ac14f2e839d723884a96e9c5fd336ebcb5da0
ms.sourcegitcommit: 30fcb35986b43388ad65dfb876eb3ad8ad0533ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799150"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="735b2-102">Installera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="735b2-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="735b2-103">Lär dig att installera Microsoft Quantum Development Kit (QDK) så att du kan komma igång med kvantprogrammering.</span><span class="sxs-lookup"><span data-stu-id="735b2-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="735b2-104">QDK består av:</span><span class="sxs-lookup"><span data-stu-id="735b2-104">The QDK consists of:</span></span>

- <span data-ttu-id="735b2-105">programmeringsspråket Q#</span><span class="sxs-lookup"><span data-stu-id="735b2-105">the Q# programming language</span></span>
- <span data-ttu-id="735b2-106">en uppsättning med bibliotek som abstraherar komplexa funktioner i Q#</span><span class="sxs-lookup"><span data-stu-id="735b2-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="735b2-107">ett värdprogram (skrivet i Python eller ett .NET-språk) som kör kvantåtgärder som har skrivits i Q#</span><span class="sxs-lookup"><span data-stu-id="735b2-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="735b2-108">verktyg som underlättar ditt utvecklingsarbete</span><span class="sxs-lookup"><span data-stu-id="735b2-108">tools to facilitate your development</span></span>

<span data-ttu-id="735b2-109">Beroende på din valda utvecklingsmiljö finns det olika installationssteg.</span><span class="sxs-lookup"><span data-stu-id="735b2-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="735b2-110">Välj din miljö i avsnitten nedan.</span><span class="sxs-lookup"><span data-stu-id="735b2-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="735b2-111">Utveckla med Python</span><span class="sxs-lookup"><span data-stu-id="735b2-111">Develop with Python</span></span>

<span data-ttu-id="735b2-112">Med qsharp-paketet för Python är det enkelt att simulera åtgärder och funktioner i Q# inifrån Python.</span><span class="sxs-lookup"><span data-stu-id="735b2-112">The qsharp package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="735b2-113">IQ# (uttalas i-q-sharp) är ett tillägg som främst används av Jupyter och Python och som ger grundläggande funktioner för att kompilera och simulera Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="735b2-113">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python that provides the core functionality for compiling and simulating Q# operations.</span></span>

1. <span data-ttu-id="735b2-114">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="735b2-114">Pre-requisites</span></span>

    - <span data-ttu-id="735b2-115">[Python](https://www.python.org/downloads/) 3.6 eller senare</span><span class="sxs-lookup"><span data-stu-id="735b2-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="735b2-116">[PIP](https://pip.pypa.io/en/stable/installing) Python-pakethanterare</span><span class="sxs-lookup"><span data-stu-id="735b2-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="735b2-117">.NET Core SDK 3.0 eller senare</span><span class="sxs-lookup"><span data-stu-id="735b2-117">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="735b2-118">Installera `qsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="735b2-118">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="735b2-119">Installera `iqsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="735b2-119">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="735b2-120">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="735b2-120">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="735b2-121">Skapa en minimal Q#-åtgärd genom att skapa en fil med namnet `Operation.qs` och lägg till följande kod i den:</span><span class="sxs-lookup"><span data-stu-id="735b2-121">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="735b2-122">Skapa ett Python-program med namnet `hello_world.py` som anropar åtgärden `SayHello()` Q#:</span><span class="sxs-lookup"><span data-stu-id="735b2-122">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="735b2-123">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="735b2-123">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="735b2-124">Verifiera utdata.</span><span class="sxs-lookup"><span data-stu-id="735b2-124">Verify the output.</span></span> <span data-ttu-id="735b2-125">Följande rader ska visas av programmet:</span><span class="sxs-lookup"><span data-stu-id="735b2-125">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="735b2-126">Utveckla med Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="735b2-126">Develop with Jupyter notebooks</span></span>

<span data-ttu-id="735b2-127">Jupyter Notebook är en favorit för akademiska inställningar, vetenskapliga labbuppgifter och onlinebaserad samverkande programmering med kodkörning lokalt – nu inklusive Q#-kod – tillsammans med instruktioner, kommentarer och annat innehåll.</span><span class="sxs-lookup"><span data-stu-id="735b2-127">A favorite of academic settings, scientific labs, and online-based collaborative programming, Jupyter Notebooks offer in-place code execution—now including Q# code—along with instructions, notes, and other content.</span></span>  <span data-ttu-id="735b2-128">Du måste göra följande för att kunna börja skapa dina egna Q#-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="735b2-128">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="735b2-129">IQ# (uttalas i-q-sharp) är ett tillägg som främst används av Jupyter och Python i .NET Core SDK, och som ger grundläggande funktioner för att kompilera och simulera Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="735b2-129">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>


1. <span data-ttu-id="735b2-130">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="735b2-130">Pre-requisites</span></span>

    - <span data-ttu-id="735b2-131">[Python](https://www.python.org/downloads/) 3.6 eller senare</span><span class="sxs-lookup"><span data-stu-id="735b2-131">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="735b2-132">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="735b2-132">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="735b2-133">.NET Core SDK 3.0 eller senare</span><span class="sxs-lookup"><span data-stu-id="735b2-133">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="735b2-134">Installera `iqsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="735b2-134">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="735b2-135">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="735b2-135">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="735b2-136">Kör följande kommando för att starta Notebook-servern:</span><span class="sxs-lookup"><span data-stu-id="735b2-136">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="735b2-137">Bläddra till den URL som visas på kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="735b2-137">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="735b2-138">Till exempel: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="735b2-138">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="735b2-139">Skapa en Jupyter Notebook med en Q#-kernel och lägg till följande kod i den första Notebook-cellen:</span><span class="sxs-lookup"><span data-stu-id="735b2-139">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="735b2-140">Kör följande Notebook-cell:</span><span class="sxs-lookup"><span data-stu-id="735b2-140">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook-cell med Q#-kod](~/media/install-guide-jupyter.png)

        <span data-ttu-id="735b2-142">Du bör se `SayHello` i cellens utdata.</span><span class="sxs-lookup"><span data-stu-id="735b2-142">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="735b2-143">När du använder Jupyter Notebook kompileras Q#-koden och Notebook visar namnet på den eller de åtgärder som den hittar.</span><span class="sxs-lookup"><span data-stu-id="735b2-143">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="735b2-144">I en ny cell simulerar du körningen i en kvantdator för den åtgärd som du nyss skapade med hjälp av `%simulate`-magic:</span><span class="sxs-lookup"><span data-stu-id="735b2-144">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

        ![Jupyter Notebook-cell med %simulate magic](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="735b2-146">Du bör se meddelandet på skärmen tillsammans med resultatet av den åtgärd du anropade (i det här fallet är det tomt).</span><span class="sxs-lookup"><span data-stu-id="735b2-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>


## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="735b2-147">Utveckla med C# i Windows med Visual Studio</span><span class="sxs-lookup"><span data-stu-id="735b2-147">Develop with C# on Windows, using Visual Studio</span></span>

<span data-ttu-id="735b2-148">I Visual Studio finns en omfattande miljö för att utveckla Q#-program, med fantastiska funktioner som kodifyllning och syntaxmarkering som hjälper utvecklarna att skapa sina program.</span><span class="sxs-lookup"><span data-stu-id="735b2-148">Visual Studio offers a rich environment for developing Q# programs, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="735b2-149">Q# Visual Studio-tillägget innehåller mallar för Q#-filer och projekt samt syntaxmarkering och stöd för IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="735b2-149">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting and IntelliSense support.</span></span>


1. <span data-ttu-id="735b2-150">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="735b2-150">Pre-requisites</span></span>

    - <span data-ttu-id="735b2-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat</span><span class="sxs-lookup"><span data-stu-id="735b2-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="735b2-152">Installera Q# Visual Studio-tillägget</span><span class="sxs-lookup"><span data-stu-id="735b2-152">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="735b2-153">Ladda ned [Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="735b2-153">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="735b2-154">Lägg till tillägget i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="735b2-154">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="735b2-155">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="735b2-155">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="735b2-156">Skapa ett nytt Q#-program</span><span class="sxs-lookup"><span data-stu-id="735b2-156">Create a new Q# application</span></span>

        - <span data-ttu-id="735b2-157">Gå till **Arkiv** -> **Nytt** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="735b2-157">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="735b2-158">Skriv `Q#` i sökrutan</span><span class="sxs-lookup"><span data-stu-id="735b2-158">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="735b2-159">Välj **Q#-program**</span><span class="sxs-lookup"><span data-stu-id="735b2-159">Select **Q# Application**</span></span>
        - <span data-ttu-id="735b2-160">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="735b2-160">Select **Next**</span></span>
        - <span data-ttu-id="735b2-161">Välj ett namn och en plats för ditt program</span><span class="sxs-lookup"><span data-stu-id="735b2-161">Choose a name and location for your application</span></span>
        - <span data-ttu-id="735b2-162">Välj **Skapa**</span><span class="sxs-lookup"><span data-stu-id="735b2-162">Select **Create**</span></span>

    - <span data-ttu-id="735b2-163">Inspektera projektet</span><span class="sxs-lookup"><span data-stu-id="735b2-163">Inspect the project</span></span>

        <span data-ttu-id="735b2-164">Du bör se att två filer har skapats: `Driver.cs`, vilket är C#-värdprogrammet och `Operation.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="735b2-164">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="735b2-165">Köra programmet</span><span class="sxs-lookup"><span data-stu-id="735b2-165">Run the application</span></span>

        - <span data-ttu-id="735b2-166">Välj **Felsökning** -> **Starta utan felsökning**</span><span class="sxs-lookup"><span data-stu-id="735b2-166">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="735b2-167">Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.</span><span class="sxs-lookup"><span data-stu-id="735b2-167">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="735b2-168">Om du har flera projekt i en Visual Studio-lösning måste alla projekt i lösningen finnas i samma mapp som lösningen, eller i en av dess undermappar.</span><span class="sxs-lookup"><span data-stu-id="735b2-168">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-visual-studio-code"></a><span data-ttu-id="735b2-169">Utveckla med C# och Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="735b2-169">Develop with C#, using Visual Studio Code</span></span>

<span data-ttu-id="735b2-170">I Visual Studio Code (VS Code) finns en omfattande miljö för att utveckla Q#-program i många olika datormiljöer, bland annat Windows, Linux och Mac. Det finns även användningsbara funktioner som kodifyllning och syntaxmarkering som hjälper utvecklarna att skapa sina program.</span><span class="sxs-lookup"><span data-stu-id="735b2-170">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="735b2-171">Q# VS Code-tillägget innehåller syntaxmarkering och Q#-kodfragment.</span><span class="sxs-lookup"><span data-stu-id="735b2-171">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

1. <span data-ttu-id="735b2-172">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="735b2-172">Pre-requisites</span></span>

   - [<span data-ttu-id="735b2-173">VS-kod</span><span class="sxs-lookup"><span data-stu-id="735b2-173">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="735b2-174">.NET Core SDK 3.0 eller senare</span><span class="sxs-lookup"><span data-stu-id="735b2-174">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="735b2-175">Installera Quantum VS Code-tillägget</span><span class="sxs-lookup"><span data-stu-id="735b2-175">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="735b2-176">Installera [VS Code-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="735b2-176">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="735b2-177">Installera Quantum-projektmallarna:</span><span class="sxs-lookup"><span data-stu-id="735b2-177">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="735b2-178">Gå till **Visa** -> **Kommandopaletten**</span><span class="sxs-lookup"><span data-stu-id="735b2-178">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="735b2-179">Välj **Q#: Installera projektmallar**</span><span class="sxs-lookup"><span data-stu-id="735b2-179">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="735b2-180">Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.</span><span class="sxs-lookup"><span data-stu-id="735b2-180">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="735b2-181">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="735b2-181">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="735b2-182">Skapa ett nytt projekt:</span><span class="sxs-lookup"><span data-stu-id="735b2-182">Create a new project:</span></span>

        - <span data-ttu-id="735b2-183">Gå till **Visa** -> **Kommandopaletten**</span><span class="sxs-lookup"><span data-stu-id="735b2-183">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="735b2-184">Välj **Q#: Skapa nytt projekt**</span><span class="sxs-lookup"><span data-stu-id="735b2-184">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="735b2-185">Gå till den plats i filsystemet där du vill skapa programmet</span><span class="sxs-lookup"><span data-stu-id="735b2-185">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="735b2-186">Klicka på knappen **Öppna nytt projekt...** när projektet har skapats</span><span class="sxs-lookup"><span data-stu-id="735b2-186">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="735b2-187">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="735b2-187">Run the application:</span></span>

        - <span data-ttu-id="735b2-188">Gå till **Felsökning** -> **Starta utan felsökning**</span><span class="sxs-lookup"><span data-stu-id="735b2-188">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="735b2-189">Du bör se följande text i utdatafönstret `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="735b2-189">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="735b2-190">Arbetsytor med flera rotmappar stöds för närvarande inte av Visual Studio Code-tillägget.</span><span class="sxs-lookup"><span data-stu-id="735b2-190">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="735b2-191">Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.</span><span class="sxs-lookup"><span data-stu-id="735b2-191">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="735b2-192">Utveckla med C# med hjälp av kommandoradsverktyget `dotnet`</span><span class="sxs-lookup"><span data-stu-id="735b2-192">Develop with C#, using the `dotnet` command-line tool</span></span>

<span data-ttu-id="735b2-193">Naturligtvis kan du också skapa och köra Q#-program från kommandoraden, genom att helt enkelt installera .NET Core SDK och QDK-projektmallarna.</span><span class="sxs-lookup"><span data-stu-id="735b2-193">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="735b2-194">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="735b2-194">Pre-requisites</span></span>

    - [<span data-ttu-id="735b2-195">.NET Core SDK 3.0 eller senare</span><span class="sxs-lookup"><span data-stu-id="735b2-195">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="735b2-196">Installera kvantprojektmallar för .NET</span><span class="sxs-lookup"><span data-stu-id="735b2-196">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="735b2-197">Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.</span><span class="sxs-lookup"><span data-stu-id="735b2-197">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="735b2-198">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="735b2-198">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="735b2-199">Skapa ett nytt program</span><span class="sxs-lookup"><span data-stu-id="735b2-199">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="735b2-200">Gå till den nya programkatalogen</span><span class="sxs-lookup"><span data-stu-id="735b2-200">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="735b2-201">Du bör se att två filer har skapats, tillsammans med projektfilerna för programmet: en Q#-fil (`Operation.qs`) och en C#-värdfil (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="735b2-201">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="735b2-202">Köra programmet</span><span class="sxs-lookup"><span data-stu-id="735b2-202">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="735b2-203">Du bör se följande utdata: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="735b2-203">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="735b2-204">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="735b2-204">What's next?</span></span>

<span data-ttu-id="735b2-205">Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="735b2-205">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
