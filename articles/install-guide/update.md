---
title: Uppdatera Quantum Development Kit (QDK)
description: 'Beskriver hur du uppdaterar dina Q #-projekt och Microsoft Quantum Development Kit till den aktuella versionen.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 53f72f1d49ae32a5a8572a1cf68a66a1d9b45e4a
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426915"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="ae210-103">Uppdatera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="ae210-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="ae210-104">Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK) till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="ae210-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="ae210-105">Den här artikeln förutsätter att du redan har installerat QDK.</span><span class="sxs-lookup"><span data-stu-id="ae210-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="ae210-106">Om du installerar för första gången kan du läsa [installations guiden](xref:microsoft.quantum.install)för.</span><span class="sxs-lookup"><span data-stu-id="ae210-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="ae210-107">Vi rekommenderar att du håller dig uppdaterad med den senaste versionen av QDK.</span><span class="sxs-lookup"><span data-stu-id="ae210-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="ae210-108">Följ den här uppdaterings guiden för att uppgradera till den senaste versionen av QDK.</span><span class="sxs-lookup"><span data-stu-id="ae210-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="ae210-109">Processen består av två delar:</span><span class="sxs-lookup"><span data-stu-id="ae210-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="ae210-110">uppdatera dina befintliga Q #-filer och-projekt för att justera koden med en uppdaterad syntax</span><span class="sxs-lookup"><span data-stu-id="ae210-110">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="ae210-111">uppdatera själva QDK för din valda utvecklings miljö</span><span class="sxs-lookup"><span data-stu-id="ae210-111">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="ae210-112">Uppdaterar Q # projekt</span><span class="sxs-lookup"><span data-stu-id="ae210-112">Updating Q# Projects</span></span> 

<span data-ttu-id="ae210-113">Följ dessa anvisningar om du vill uppdatera dina Q #-projekt oavsett om du använder C# eller python som värd för Q #-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="ae210-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="ae210-114">Kontrol lera först att du har den senaste versionen av [.NET Core SDK 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="ae210-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="ae210-115">Kör följande kommando i kommando tolken:</span><span class="sxs-lookup"><span data-stu-id="ae210-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="ae210-116">Kontrol lera att utdata är `3.1.100` eller högre.</span><span class="sxs-lookup"><span data-stu-id="ae210-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="ae210-117">Om inte, installerar du den [senaste versionen](https://dotnet.microsoft.com/download) och kontrollerar igen.</span><span class="sxs-lookup"><span data-stu-id="ae210-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="ae210-118">Följ sedan anvisningarna nedan beroende på dina inställningar (Visual Studio, Visual Studio Code eller direkt på kommando raden).</span><span class="sxs-lookup"><span data-stu-id="ae210-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="ae210-119">Uppdatera Q #-projekt i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ae210-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="ae210-120">Uppdatera till den senaste versionen av Visual Studio 2019 finns [här](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) för instruktioner</span><span class="sxs-lookup"><span data-stu-id="ae210-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="ae210-121">Öppna din lösning i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ae210-121">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="ae210-122">Välj **Bygg**  ->  **ren lösning** på menyn</span><span class="sxs-lookup"><span data-stu-id="ae210-122">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="ae210-123">I var och en av dina. CSPROJ-filer uppdaterar du mål ramverket till `netcoreapp3.1` (eller `netstandard2.1` om det är ett biblioteks projekt).</span><span class="sxs-lookup"><span data-stu-id="ae210-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="ae210-124">Det vill säga Redigera rader i formuläret:</span><span class="sxs-lookup"><span data-stu-id="ae210-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="ae210-125">Du hittar mer information om att ange mål ramverk [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="ae210-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="ae210-126">Spara och Stäng alla filer i lösningen</span><span class="sxs-lookup"><span data-stu-id="ae210-126">Save and close all files in your solution</span></span>
6. <span data-ttu-id="ae210-127">Välj **verktyg**  ->  **kommando rad**  ->  **utvecklare kommando tolk**</span><span class="sxs-lookup"><span data-stu-id="ae210-127">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="ae210-128">Kör följande kommando för varje projekt i lösningen:</span><span class="sxs-lookup"><span data-stu-id="ae210-128">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="ae210-129">Om dina projekt använder andra Microsoft. Quantum-paket (t. ex. Microsoft. Quantum. numeric) kör du kommandot för dessa.</span><span class="sxs-lookup"><span data-stu-id="ae210-129">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="ae210-130">Stäng kommando tolken och välj **skapa**  ->  **build-lösning** (Välj *inte* att återskapa lösningen)</span><span class="sxs-lookup"><span data-stu-id="ae210-130">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="ae210-131">Nu kan du gå vidare till [Uppdatera ditt Visual Studio QDK-tillägg](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="ae210-131">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="ae210-132">Uppdatera Q #-projekt i Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ae210-132">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="ae210-133">Öppna mappen som innehåller projektet som ska uppdateras i Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ae210-133">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="ae210-134">Välj **Terminal**,  ->  **ny terminal**</span><span class="sxs-lookup"><span data-stu-id="ae210-134">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="ae210-135">Följ anvisningarna för uppdatering med hjälp av kommando raden (direkt nedan)</span><span class="sxs-lookup"><span data-stu-id="ae210-135">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="ae210-136">Uppdatera Q #-projekt med hjälp av kommando raden</span><span class="sxs-lookup"><span data-stu-id="ae210-136">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="ae210-137">Navigera till mappen som innehåller projekt filen</span><span class="sxs-lookup"><span data-stu-id="ae210-137">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="ae210-138">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ae210-138">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="ae210-139">I var och en av dina. CSPROJ-filer uppdaterar du mål ramverket till `netcoreapp3.1` (eller `netstandard2.1` om det är ett biblioteks projekt).</span><span class="sxs-lookup"><span data-stu-id="ae210-139">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="ae210-140">Det vill säga Redigera rader i formuläret:</span><span class="sxs-lookup"><span data-stu-id="ae210-140">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="ae210-141">Du hittar mer information om att ange mål ramverk [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="ae210-141">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="ae210-142">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ae210-142">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="ae210-143">Om projektet använder andra Microsoft. Quantum-paket (t. ex. Microsoft. Quantum. numeric) kör du kommandot för dessa.</span><span class="sxs-lookup"><span data-stu-id="ae210-143">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="ae210-144">Spara och Stäng alla filer.</span><span class="sxs-lookup"><span data-stu-id="ae210-144">Save and close all files.</span></span>
6. <span data-ttu-id="ae210-145">Upprepa 1-4 för varje projekt beroende och gå sedan tillbaka till mappen som innehåller huvud projektet och kör:</span><span class="sxs-lookup"><span data-stu-id="ae210-145">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="ae210-146">När du har uppdaterat dina Q #-projekt följer du anvisningarna nedan för att uppdatera själva QDK.</span><span class="sxs-lookup"><span data-stu-id="ae210-146">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="ae210-147">Uppdaterar QDK</span><span class="sxs-lookup"><span data-stu-id="ae210-147">Updating the QDK</span></span>

<span data-ttu-id="ae210-148">Processen för att uppdatera QDK varierar beroende på ditt utvecklings språk och miljö.</span><span class="sxs-lookup"><span data-stu-id="ae210-148">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="ae210-149">Välj din utvecklings miljö nedan.</span><span class="sxs-lookup"><span data-stu-id="ae210-149">Select your development environment below.</span></span>

* [<span data-ttu-id="ae210-150">Python: uppdatera SWEETIQ #-tillägget</span><span class="sxs-lookup"><span data-stu-id="ae210-150">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="ae210-151">Jupyter Notebook: uppdatera SWEETIQ #-tillägget</span><span class="sxs-lookup"><span data-stu-id="ae210-151">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="ae210-152">Visual Studio: uppdatera tillägget QDK</span><span class="sxs-lookup"><span data-stu-id="ae210-152">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="ae210-153">VS Code: uppdatera tillägget QDK</span><span class="sxs-lookup"><span data-stu-id="ae210-153">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="ae210-154">Kommando rad och C#: uppdatera projektmallar</span><span class="sxs-lookup"><span data-stu-id="ae210-154">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="ae210-155">Uppdatera SWEETIQ # för python</span><span class="sxs-lookup"><span data-stu-id="ae210-155">Update IQ# for Python</span></span>

1. <span data-ttu-id="ae210-156">Uppdatera `iqsharp` kerneln</span><span class="sxs-lookup"><span data-stu-id="ae210-156">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="ae210-157">Verifiera `iqsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="ae210-157">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="ae210-158">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="ae210-158">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="ae210-159">Oroa dig inte om din `iqsharp` version är högre, den ska överensstämma med den [senaste versionen](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="ae210-159">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="ae210-160">Uppdatera `qsharp` paketet</span><span class="sxs-lookup"><span data-stu-id="ae210-160">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="ae210-161">Verifiera `qsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="ae210-161">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="ae210-162">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="ae210-162">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="ae210-163">Kör följande kommando från platsen för dina `.qs` filer</span><span class="sxs-lookup"><span data-stu-id="ae210-163">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="ae210-164">Nu kan du använda den uppdaterade QDK-versionen för att köra befintliga Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="ae210-164">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="ae210-165">Uppdatera SWEETIQ # för Jupyter-anteckningsböcker</span><span class="sxs-lookup"><span data-stu-id="ae210-165">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="ae210-166">Uppdatera `iqsharp` kerneln</span><span class="sxs-lookup"><span data-stu-id="ae210-166">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="ae210-167">Verifiera `iqsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="ae210-167">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="ae210-168">Dina utdata bör likna följande:</span><span class="sxs-lookup"><span data-stu-id="ae210-168">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="ae210-169">Oroa dig inte om din `iqsharp` version är högre, den ska överensstämma med den [senaste versionen](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="ae210-169">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="ae210-170">Kör följande kommando från en cell i Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="ae210-170">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="ae210-171">Nu kan du öppna en befintlig Jupyter-anteckningsbok och köra den med den uppdaterade QDK.</span><span class="sxs-lookup"><span data-stu-id="ae210-171">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="ae210-172">Uppdatera Visual Studio QDK-tillägg</span><span class="sxs-lookup"><span data-stu-id="ae210-172">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="ae210-173">Uppdatera Q # Visual Studio-tillägget</span><span class="sxs-lookup"><span data-stu-id="ae210-173">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="ae210-174">Visual Studio efterfrågar att du accepterar uppdateringar av [Quantum Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="ae210-174">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="ae210-175">Godkänn uppdateringen</span><span class="sxs-lookup"><span data-stu-id="ae210-175">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="ae210-176">Projektfilerna uppdateras med tillägget.</span><span class="sxs-lookup"><span data-stu-id="ae210-176">The project templates are updated with the extension.</span></span> <span data-ttu-id="ae210-177">De uppdaterade mallarna gäller endast för nyligen skapade projekt.</span><span class="sxs-lookup"><span data-stu-id="ae210-177">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="ae210-178">Koden för dina befintliga projekt uppdateras inte när tillägget uppdateras.</span><span class="sxs-lookup"><span data-stu-id="ae210-178">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="ae210-179">Uppdatera VS Code QDK-tillägg</span><span class="sxs-lookup"><span data-stu-id="ae210-179">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="ae210-180">Uppdatera tillägget för Quantum VS Code</span><span class="sxs-lookup"><span data-stu-id="ae210-180">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="ae210-181">Starta om VS-kod</span><span class="sxs-lookup"><span data-stu-id="ae210-181">Restart VS Code</span></span>
    - <span data-ttu-id="ae210-182">Navigera till fliken **tillägg**</span><span class="sxs-lookup"><span data-stu-id="ae210-182">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="ae210-183">Välj **Microsoft Quantum Development Kit för Visual Studio Code** -tillägg</span><span class="sxs-lookup"><span data-stu-id="ae210-183">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="ae210-184">Läs in tillägget igen</span><span class="sxs-lookup"><span data-stu-id="ae210-184">Reload the extension</span></span>

2. <span data-ttu-id="ae210-185">Uppdatera Quantum-projektmallar:</span><span class="sxs-lookup"><span data-stu-id="ae210-185">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="ae210-186">Gå till **Visa**  ->  **kommando palett**</span><span class="sxs-lookup"><span data-stu-id="ae210-186">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="ae210-187">Välj **Q #: installera projektmallar**</span><span class="sxs-lookup"><span data-stu-id="ae210-187">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="ae210-188">Efter några sekunder bör du få ett popup-meddelande om att Project-mallar har installerats</span><span class="sxs-lookup"><span data-stu-id="ae210-188">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="ae210-189">C# med `dotnet` kommando rads verktyget</span><span class="sxs-lookup"><span data-stu-id="ae210-189">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="ae210-190">Uppdatera Quantum Project-mallar för .NET</span><span class="sxs-lookup"><span data-stu-id="ae210-190">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```