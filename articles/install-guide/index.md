---
title: Lär dig att installera Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 090cf98612c6c549c733e54f9dcbf74442b30fbd
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442252"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="297df-102">Installera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="297df-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="297df-103">Lär dig att installera Microsoft Quantum Development Kit (QDK) så att du kan komma igång med kvantprogrammering.</span><span class="sxs-lookup"><span data-stu-id="297df-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="297df-104">QDK består av:</span><span class="sxs-lookup"><span data-stu-id="297df-104">The QDK consists of:</span></span>

- <span data-ttu-id="297df-105">programmeringsspråket Q#</span><span class="sxs-lookup"><span data-stu-id="297df-105">the Q# programming language</span></span>
- <span data-ttu-id="297df-106">en uppsättning med bibliotek som abstraherar komplexa funktioner i Q#</span><span class="sxs-lookup"><span data-stu-id="297df-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="297df-107">ett värdprogram (skrivet i Python eller ett .NET-språk) som kör kvantåtgärder som har skrivits i Q#</span><span class="sxs-lookup"><span data-stu-id="297df-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="297df-108">verktyg som underlättar ditt utvecklingsarbete</span><span class="sxs-lookup"><span data-stu-id="297df-108">tools to facilitate your development</span></span>

<span data-ttu-id="297df-109">Beroende på din valda utvecklingsmiljö finns det olika installationssteg.</span><span class="sxs-lookup"><span data-stu-id="297df-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="297df-110">Välj din miljö i avsnitten nedan.</span><span class="sxs-lookup"><span data-stu-id="297df-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="297df-111">Utveckla med Python</span><span class="sxs-lookup"><span data-stu-id="297df-111">Develop with Python</span></span>

<span data-ttu-id="297df-112">Med qsharp-paketet för Python är det enkelt att simulera åtgärder och funktioner i Q# inifrån Python.</span><span class="sxs-lookup"><span data-stu-id="297df-112">The qsharp package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="297df-113">IQ# (uttalas i-q-sharp) är ett tillägg som främst används av Jupyter och Python och som ger grundläggande funktioner för att kompilera och simulera Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="297df-113">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python that provides the core functionality for compiling and simulating Q# operations.</span></span>

1. <span data-ttu-id="297df-114">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="297df-114">Pre-requisites</span></span>

    - <span data-ttu-id="297df-115">[Python](https://www.python.org/downloads/) 3.6 eller senare</span><span class="sxs-lookup"><span data-stu-id="297df-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="297df-116">[PIP](https://pip.pypa.io/en/stable/installing) Python-pakethanterare</span><span class="sxs-lookup"><span data-stu-id="297df-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="297df-117">.NET Core SDK 3.0 eller senare</span><span class="sxs-lookup"><span data-stu-id="297df-117">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="297df-118">Installera `iqsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="297df-118">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="297df-119">Installera `qsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="297df-119">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="297df-120">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="297df-120">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="297df-121">Skapa en minimal Q#-åtgärd genom att skapa en fil med namnet `Operation.qs` och lägg till följande kod i den:</span><span class="sxs-lookup"><span data-stu-id="297df-121">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="297df-122">Skapa ett Python-program med namnet `hello_world.py` som anropar åtgärden `SayHello()` Q#:</span><span class="sxs-lookup"><span data-stu-id="297df-122">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="297df-123">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="297df-123">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="297df-124">Verifiera utdata.</span><span class="sxs-lookup"><span data-stu-id="297df-124">Verify the output.</span></span> <span data-ttu-id="297df-125">Följande rader ska visas av programmet:</span><span class="sxs-lookup"><span data-stu-id="297df-125">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="297df-126">Utveckla med Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="297df-126">Develop with Jupyter notebooks</span></span>

<span data-ttu-id="297df-127">Jupyter Notebook är en favorit för akademiska inställningar, vetenskapliga labbuppgifter och onlinebaserad samverkande programmering med kodkörning lokalt – nu inklusive Q#-kod – tillsammans med instruktioner, kommentarer och annat innehåll.</span><span class="sxs-lookup"><span data-stu-id="297df-127">A favorite of academic settings, scientific labs, and online-based collaborative programming, Jupyter Notebooks offer in-place code execution—now including Q# code—along with instructions, notes, and other content.</span></span>  <span data-ttu-id="297df-128">Du måste göra följande för att kunna börja skapa dina egna Q#-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="297df-128">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="297df-129">IQ# (uttalas i-q-sharp) är ett tillägg som främst används av Jupyter och Python i .NET Core SDK, och som ger grundläggande funktioner för att kompilera och simulera Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="297df-129">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>


1. <span data-ttu-id="297df-130">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="297df-130">Pre-requisites</span></span>

    - <span data-ttu-id="297df-131">[Python](https://www.python.org/downloads/) 3.6 eller senare</span><span class="sxs-lookup"><span data-stu-id="297df-131">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="297df-132">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="297df-132">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="297df-133">.NET Core SDK 3.0 eller senare</span><span class="sxs-lookup"><span data-stu-id="297df-133">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="297df-134">Installera `iqsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="297df-134">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="297df-135">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="297df-135">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="297df-136">Kör följande kommando för att starta Notebook-servern:</span><span class="sxs-lookup"><span data-stu-id="297df-136">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="297df-137">Bläddra till den URL som visas på kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="297df-137">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="297df-138">Till exempel: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="297df-138">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="297df-139">Skapa en Jupyter Notebook med en Q#-kernel och lägg till följande kod i den första Notebook-cellen:</span><span class="sxs-lookup"><span data-stu-id="297df-139">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="297df-140">Kör följande Notebook-cell:</span><span class="sxs-lookup"><span data-stu-id="297df-140">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook-cell med Q#-kod](~/media/install-guide-jupyter.png)

        <span data-ttu-id="297df-142">Du bör se `SayHello` i cellens utdata.</span><span class="sxs-lookup"><span data-stu-id="297df-142">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="297df-143">När du använder Jupyter Notebook kompileras Q#-koden och Notebook visar namnet på den eller de åtgärder som den hittar.</span><span class="sxs-lookup"><span data-stu-id="297df-143">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="297df-144">I en ny cell simulerar du körningen i en kvantdator för den åtgärd som du nyss skapade med hjälp av `%simulate`-magic:</span><span class="sxs-lookup"><span data-stu-id="297df-144">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

        ![Jupyter Notebook-cell med %simulate magic](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="297df-146">Du bör se meddelandet på skärmen tillsammans med resultatet av den åtgärd du anropade (i det här fallet är det tomt).</span><span class="sxs-lookup"><span data-stu-id="297df-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>


## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="297df-147">Utveckla med C# i Windows med Visual Studio</span><span class="sxs-lookup"><span data-stu-id="297df-147">Develop with C# on Windows, using Visual Studio</span></span>

<span data-ttu-id="297df-148">I Visual Studio finns en omfattande miljö för att utveckla Q#-program, med fantastiska funktioner som kodifyllning och syntaxmarkering som hjälper utvecklarna att skapa sina program.</span><span class="sxs-lookup"><span data-stu-id="297df-148">Visual Studio offers a rich environment for developing Q# programs, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="297df-149">Q# Visual Studio-tillägget innehåller mallar för Q#-filer och projekt samt syntaxmarkering och stöd för IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="297df-149">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting and IntelliSense support.</span></span>


1. <span data-ttu-id="297df-150">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="297df-150">Pre-requisites</span></span>

    - <span data-ttu-id="297df-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat</span><span class="sxs-lookup"><span data-stu-id="297df-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="297df-152">Installera Q# Visual Studio-tillägget</span><span class="sxs-lookup"><span data-stu-id="297df-152">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="297df-153">Ladda ned [Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="297df-153">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="297df-154">Lägg till tillägget i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="297df-154">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="297df-155">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="297df-155">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="297df-156">Skapa ett nytt Q#-program</span><span class="sxs-lookup"><span data-stu-id="297df-156">Create a new Q# application</span></span>

        - <span data-ttu-id="297df-157">Gå till **Arkiv** -> **Nytt** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="297df-157">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="297df-158">Skriv `Q#` i sökrutan</span><span class="sxs-lookup"><span data-stu-id="297df-158">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="297df-159">Välj **Q#-program**</span><span class="sxs-lookup"><span data-stu-id="297df-159">Select **Q# Application**</span></span>
        - <span data-ttu-id="297df-160">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="297df-160">Select **Next**</span></span>
        - <span data-ttu-id="297df-161">Välj ett namn och en plats för ditt program</span><span class="sxs-lookup"><span data-stu-id="297df-161">Choose a name and location for your application</span></span>
        - <span data-ttu-id="297df-162">Välj **Skapa**</span><span class="sxs-lookup"><span data-stu-id="297df-162">Select **Create**</span></span>

    - <span data-ttu-id="297df-163">Inspektera projektet</span><span class="sxs-lookup"><span data-stu-id="297df-163">Inspect the project</span></span>

        <span data-ttu-id="297df-164">Du bör se att två filer har skapats: `Driver.cs`, vilket är C#-värdprogrammet och `Operation.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="297df-164">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="297df-165">Köra programmet</span><span class="sxs-lookup"><span data-stu-id="297df-165">Run the application</span></span>

        - <span data-ttu-id="297df-166">Välj **Felsökning** -> **Starta utan felsökning**</span><span class="sxs-lookup"><span data-stu-id="297df-166">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="297df-167">Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.</span><span class="sxs-lookup"><span data-stu-id="297df-167">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="297df-168">Om du har flera projekt i en Visual Studio-lösning måste alla projekt i lösningen finnas i samma mapp som lösningen, eller i en av dess undermappar.</span><span class="sxs-lookup"><span data-stu-id="297df-168">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-visual-studio-code"></a><span data-ttu-id="297df-169">Utveckla med C# och Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="297df-169">Develop with C#, using Visual Studio Code</span></span>

<span data-ttu-id="297df-170">I Visual Studio Code (VS Code) finns en omfattande miljö för att utveckla Q#-program i många olika datormiljöer, bland annat Windows, Linux och Mac. Det finns även användningsbara funktioner som kodifyllning och syntaxmarkering som hjälper utvecklarna att skapa sina program.</span><span class="sxs-lookup"><span data-stu-id="297df-170">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="297df-171">Q# VS Code-tillägget innehåller syntaxmarkering och Q#-kodfragment.</span><span class="sxs-lookup"><span data-stu-id="297df-171">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

<span data-ttu-id="297df-172">I Visual Studio Code (VS Code) finns en omfattande miljö för att utveckla Q#-program i många olika datormiljöer, bland annat Windows, Linux och Mac. Det finns även användningsbara funktioner som kodifyllning och syntaxmarkering som hjälper utvecklarna att skapa sina program.</span><span class="sxs-lookup"><span data-stu-id="297df-172">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="297df-173">Q# VS Code-tillägget innehåller syntaxmarkering och Q#-kodfragment.</span><span class="sxs-lookup"><span data-stu-id="297df-173">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

1. <span data-ttu-id="297df-174">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="297df-174">Pre-requisites</span></span>

   - [<span data-ttu-id="297df-175">VS-kod</span><span class="sxs-lookup"><span data-stu-id="297df-175">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="297df-176">.NET Core SDK 3.0 eller senare</span><span class="sxs-lookup"><span data-stu-id="297df-176">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="297df-177">Installera Quantum VS Code-tillägget</span><span class="sxs-lookup"><span data-stu-id="297df-177">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="297df-178">Installera [VS Code-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="297df-178">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="297df-179">Installera Quantum-projektmallarna:</span><span class="sxs-lookup"><span data-stu-id="297df-179">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="297df-180">Gå till **Visa** -> **Kommandopaletten**</span><span class="sxs-lookup"><span data-stu-id="297df-180">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="297df-181">Välj **Q#: Installera projektmallar**</span><span class="sxs-lookup"><span data-stu-id="297df-181">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="297df-182">Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.</span><span class="sxs-lookup"><span data-stu-id="297df-182">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="297df-183">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="297df-183">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="297df-184">Skapa ett nytt projekt:</span><span class="sxs-lookup"><span data-stu-id="297df-184">Create a new project:</span></span>

        - <span data-ttu-id="297df-185">Gå till **Visa** -> **Kommandopaletten**</span><span class="sxs-lookup"><span data-stu-id="297df-185">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="297df-186">Välj **Q#: Skapa nytt projekt**</span><span class="sxs-lookup"><span data-stu-id="297df-186">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="297df-187">Gå till den plats i filsystemet där du vill skapa programmet</span><span class="sxs-lookup"><span data-stu-id="297df-187">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="297df-188">Klicka på knappen **Öppna nytt projekt...** när projektet har skapats</span><span class="sxs-lookup"><span data-stu-id="297df-188">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="297df-189">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="297df-189">Run the application:</span></span>

        - <span data-ttu-id="297df-190">Gå till **Felsökning** -> **Starta utan felsökning**</span><span class="sxs-lookup"><span data-stu-id="297df-190">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="297df-191">Du bör se följande text i utdatafönstret `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="297df-191">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="297df-192">Arbetsytor med flera rotmappar stöds för närvarande inte av Visual Studio Code-tillägget.</span><span class="sxs-lookup"><span data-stu-id="297df-192">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="297df-193">Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.</span><span class="sxs-lookup"><span data-stu-id="297df-193">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="297df-194">Utveckla med C# med hjälp av kommandoradsverktyget `dotnet`</span><span class="sxs-lookup"><span data-stu-id="297df-194">Develop with C#, using the `dotnet` command-line tool</span></span>

<span data-ttu-id="297df-195">Naturligtvis kan du också skapa och köra Q#-program från kommandoraden, genom att helt enkelt installera .NET Core SDK och QDK-projektmallarna.</span><span class="sxs-lookup"><span data-stu-id="297df-195">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="297df-196">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="297df-196">Pre-requisites</span></span>

    - [<span data-ttu-id="297df-197">.NET Core SDK 3.0 eller senare</span><span class="sxs-lookup"><span data-stu-id="297df-197">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="297df-198">Installera kvantprojektmallar för .NET</span><span class="sxs-lookup"><span data-stu-id="297df-198">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="297df-199">Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.</span><span class="sxs-lookup"><span data-stu-id="297df-199">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="297df-200">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="297df-200">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="297df-201">Skapa ett nytt program</span><span class="sxs-lookup"><span data-stu-id="297df-201">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="297df-202">Gå till den nya programkatalogen</span><span class="sxs-lookup"><span data-stu-id="297df-202">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="297df-203">Du bör se att två filer har skapats, tillsammans med projektfilerna för programmet: en Q#-fil (`Operation.qs`) och en C#-värdfil (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="297df-203">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="297df-204">Köra programmet</span><span class="sxs-lookup"><span data-stu-id="297df-204">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="297df-205">Du bör se följande utdata: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="297df-205">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="297df-206">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="297df-206">What's next?</span></span>

<span data-ttu-id="297df-207">Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="297df-207">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
