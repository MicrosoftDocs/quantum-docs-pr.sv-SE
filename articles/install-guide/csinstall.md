---
title: 'Utveckla med Q # +C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 7803846279f230f5fc0ee8424bd39be735a650ca
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036295"
---
# <a name="develop-with-q--c"></a><span data-ttu-id="4ac1e-102">Utveckla med Q # +C#</span><span class="sxs-lookup"><span data-stu-id="4ac1e-102">Develop with Q# + C#</span></span>

<span data-ttu-id="4ac1e-103">Installera QDK för att utveckla C# värd program för att anropa Q #-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-103">Install the QDK to develop C# host programs to call Q# operations.</span></span>

<span data-ttu-id="4ac1e-104">Q # är utformat för att spela bra med .NET-språk – C#särskilt.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-104">Q# is built to play well with .NET languages--specifically C#.</span></span> <span data-ttu-id="4ac1e-105">Du kan arbeta med denna koppling i olika utvecklings miljöer:</span><span class="sxs-lookup"><span data-stu-id="4ac1e-105">You can work with this pairing inside different development environments:</span></span>

- [<span data-ttu-id="4ac1e-106">Q # + C# använda Visual Studio (Windows)</span><span class="sxs-lookup"><span data-stu-id="4ac1e-106">Q# + C# using Visual Studio (Windows)</span></span>](#VS)
- [<span data-ttu-id="4ac1e-107">Q # + C# använda Visual Studio Code (Windows, Linux och Mac)</span><span class="sxs-lookup"><span data-stu-id="4ac1e-107">Q# + C# using Visual Studio Code (Windows, Linux and Mac)</span></span>](#VSC)
- [<span data-ttu-id="4ac1e-108">Q # + C# använda kommando rads verktyget `dotnet`</span><span class="sxs-lookup"><span data-stu-id="4ac1e-108">Q# + C# using the `dotnet` command-line tool</span></span>](#command)

## <span data-ttu-id="4ac1e-109">Utveckla med Q # + C# med Visual Studio <a name="VS"></a></span><span class="sxs-lookup"><span data-stu-id="4ac1e-109">Develop with Q# + C# using Visual Studio <a name="VS"></a></span></span>

<span data-ttu-id="4ac1e-110">Visual Studio erbjuder en omfattande miljö för att utveckla Q #-program.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-110">Visual Studio offers a rich environment for developing Q# programs.</span></span> <span data-ttu-id="4ac1e-111">Q # Visual Studio-tillägget innehåller mallar för Q #-filer och-projekt samt markering av syntax, kod komplettering och stöd för IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-111">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting, code completion and IntelliSense support.</span></span>


1. <span data-ttu-id="4ac1e-112">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4ac1e-112">Pre-requisites</span></span>

    - <span data-ttu-id="4ac1e-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat</span><span class="sxs-lookup"><span data-stu-id="4ac1e-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="4ac1e-114">Installera Q# Visual Studio-tillägget</span><span class="sxs-lookup"><span data-stu-id="4ac1e-114">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="4ac1e-115">Ladda ned och installera [Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="4ac1e-115">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>

1. <span data-ttu-id="4ac1e-116">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="4ac1e-116">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4ac1e-117">Skapa ett nytt Q#-program</span><span class="sxs-lookup"><span data-stu-id="4ac1e-117">Create a new Q# application</span></span>

        - <span data-ttu-id="4ac1e-118">Gå till **Arkiv** -> **Nytt** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="4ac1e-118">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="4ac1e-119">Skriv `Q#` i sökrutan</span><span class="sxs-lookup"><span data-stu-id="4ac1e-119">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="4ac1e-120">Välj **Q#-program**</span><span class="sxs-lookup"><span data-stu-id="4ac1e-120">Select **Q# Application**</span></span>
        - <span data-ttu-id="4ac1e-121">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="4ac1e-121">Select **Next**</span></span>
        - <span data-ttu-id="4ac1e-122">Välj ett namn och en plats för ditt program</span><span class="sxs-lookup"><span data-stu-id="4ac1e-122">Choose a name and location for your application</span></span>
        - <span data-ttu-id="4ac1e-123">Välj **Skapa**</span><span class="sxs-lookup"><span data-stu-id="4ac1e-123">Select **Create**</span></span>

    - <span data-ttu-id="4ac1e-124">Inspektera projektet</span><span class="sxs-lookup"><span data-stu-id="4ac1e-124">Inspect the project</span></span>

        <span data-ttu-id="4ac1e-125">Du bör se att två filer har skapats: `Driver.cs`, vilket är C#-värdprogrammet och `Operation.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-125">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="4ac1e-126">Köra programmet</span><span class="sxs-lookup"><span data-stu-id="4ac1e-126">Run the application</span></span>

        - <span data-ttu-id="4ac1e-127">Välj **Felsökning** -> **Starta utan felsökning**</span><span class="sxs-lookup"><span data-stu-id="4ac1e-127">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="4ac1e-128">Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-128">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="4ac1e-129">Om du har flera projekt i en Visual Studio-lösning måste alla projekt i lösningen finnas i samma mapp som lösningen, eller i en av dess undermappar.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-129">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <span data-ttu-id="4ac1e-130">Utveckla med Q # + C# med Visual Studio Code <a name="VSC"></a></span><span class="sxs-lookup"><span data-stu-id="4ac1e-130">Develop with Q# + C# using Visual Studio Code <a name="VSC"></a></span></span>

<span data-ttu-id="4ac1e-131">Visual Studio Code (VS Code) erbjuder en omfattande miljö för att utveckla Q #-program på Windows, Linux och Mac.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-131">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs on Windows, Linux and Mac.</span></span>  <span data-ttu-id="4ac1e-132">Q # VS Code-tillägget innehåller stöd för markering av Q #-syntax, kod komplettering och Q #-kodfragment.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-132">The Q# VS Code extension includes support for Q# syntax highlighting, code completion, and Q# code snippets.</span></span>

1. <span data-ttu-id="4ac1e-133">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4ac1e-133">Pre-requisites</span></span>

   - [<span data-ttu-id="4ac1e-134">VS-kod</span><span class="sxs-lookup"><span data-stu-id="4ac1e-134">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="4ac1e-135">.NET Core SDK 3,1 eller senare</span><span class="sxs-lookup"><span data-stu-id="4ac1e-135">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4ac1e-136">Installera Quantum VS Code-tillägget</span><span class="sxs-lookup"><span data-stu-id="4ac1e-136">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="4ac1e-137">Installera [VS Code-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="4ac1e-137">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="4ac1e-138">Installera Quantum-projektmallarna:</span><span class="sxs-lookup"><span data-stu-id="4ac1e-138">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="4ac1e-139">Gå till **Visa** -> **Kommandopaletten**</span><span class="sxs-lookup"><span data-stu-id="4ac1e-139">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="4ac1e-140">Välj **Q #: installera projektmallar**</span><span class="sxs-lookup"><span data-stu-id="4ac1e-140">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="4ac1e-141">Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-141">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="4ac1e-142">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="4ac1e-142">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4ac1e-143">Skapa ett nytt projekt:</span><span class="sxs-lookup"><span data-stu-id="4ac1e-143">Create a new project:</span></span>

        - <span data-ttu-id="4ac1e-144">Gå till **Visa** -> **Kommandopaletten**</span><span class="sxs-lookup"><span data-stu-id="4ac1e-144">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="4ac1e-145">Välj **Q #: skapa nytt projekt**</span><span class="sxs-lookup"><span data-stu-id="4ac1e-145">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="4ac1e-146">Välj **fristående konsol program**</span><span class="sxs-lookup"><span data-stu-id="4ac1e-146">Select **Standalone console application**</span></span>
        - <span data-ttu-id="4ac1e-147">Gå till den plats i filsystemet där du vill skapa programmet</span><span class="sxs-lookup"><span data-stu-id="4ac1e-147">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="4ac1e-148">Klicka på knappen **Öppna nytt projekt...** när projektet har skapats</span><span class="sxs-lookup"><span data-stu-id="4ac1e-148">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="4ac1e-149">Om du inte redan har installerat C# tillägget vs Code visas ett popup-fönster.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-149">If you don't already have the C# extension for VS Code installed, a pop-up will appear.</span></span> <span data-ttu-id="4ac1e-150">Installera tillägget.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-150">Install the extension.</span></span> 

    - <span data-ttu-id="4ac1e-151">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="4ac1e-151">Run the application:</span></span>

        - <span data-ttu-id="4ac1e-152">Gå till **terminal** -> **ny terminal**</span><span class="sxs-lookup"><span data-stu-id="4ac1e-152">Go to **Terminal** -> **New Terminal**</span></span>
        - <span data-ttu-id="4ac1e-153">Ange `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="4ac1e-153">Enter `dotnet run`</span></span>
        - <span data-ttu-id="4ac1e-154">Du bör se följande text i utdatafönstret `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="4ac1e-154">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="4ac1e-155">Arbetsytor med flera rotmappar stöds för närvarande inte av Visual Studio Code-tillägget.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-155">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="4ac1e-156">Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-156">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <span data-ttu-id="4ac1e-157">Utveckla med Q # + C# med hjälp av kommando rads verktyget `dotnet`<a name="command"></a></span><span class="sxs-lookup"><span data-stu-id="4ac1e-157">Develop with Q# + C# using the `dotnet` command-line tool <a name="command"></a></span></span>

<span data-ttu-id="4ac1e-158">Naturligtvis kan du också skapa och köra Q#-program från kommandoraden, genom att helt enkelt installera .NET Core SDK och QDK-projektmallarna.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-158">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="4ac1e-159">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4ac1e-159">Pre-requisites</span></span>

    - [<span data-ttu-id="4ac1e-160">.NET Core SDK 3,1 eller senare</span><span class="sxs-lookup"><span data-stu-id="4ac1e-160">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4ac1e-161">Installera kvantprojektmallar för .NET</span><span class="sxs-lookup"><span data-stu-id="4ac1e-161">Install the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="4ac1e-162">Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.</span><span class="sxs-lookup"><span data-stu-id="4ac1e-162">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="4ac1e-163">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="4ac1e-163">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4ac1e-164">Skapa ett nytt program</span><span class="sxs-lookup"><span data-stu-id="4ac1e-164">Create a new application</span></span>

       ```dotnetcli
       dotnet new console -lang "Q#" -o runSayHello
       ```

    - <span data-ttu-id="4ac1e-165">Gå till den nya programkatalogen</span><span class="sxs-lookup"><span data-stu-id="4ac1e-165">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="4ac1e-166">Du bör se att två filer har skapats, tillsammans med projektfilerna för programmet: en Q#-fil (`Operation.qs`) och en C#-värdfil (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="4ac1e-166">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="4ac1e-167">Köra programmet</span><span class="sxs-lookup"><span data-stu-id="4ac1e-167">Run the application</span></span>

        ```dotnetcli
        dotnet run
        ```

        <span data-ttu-id="4ac1e-168">Du bör se följande utdata: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="4ac1e-168">You should see the following output: `Hello quantum world!`</span></span>

    
## <a name="whats-next"></a><span data-ttu-id="4ac1e-169">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4ac1e-169">What's next?</span></span>

<span data-ttu-id="4ac1e-170">Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="4ac1e-170">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
