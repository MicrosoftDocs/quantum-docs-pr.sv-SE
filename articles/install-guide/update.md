---
title: Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ed2a90749bbe245dde97424fc3191682f995d85b
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819747"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="64ab7-102">Uppdatera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="64ab7-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="64ab7-103">Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK) till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="64ab7-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="64ab7-104">Den här artikeln förutsätter att du redan har installerat QDK.</span><span class="sxs-lookup"><span data-stu-id="64ab7-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="64ab7-105">Om du installerar för första gången kan du läsa [installations guiden](xref:microsoft.quantum.install)för.</span><span class="sxs-lookup"><span data-stu-id="64ab7-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="64ab7-106">Vi rekommenderar att du håller dig uppdaterad med den senaste versionen av QDK.</span><span class="sxs-lookup"><span data-stu-id="64ab7-106">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="64ab7-107">Följ den här uppdaterings guiden för att uppgradera till den senaste versionen av QDK.</span><span class="sxs-lookup"><span data-stu-id="64ab7-107">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="64ab7-108">Processen består av två delar:</span><span class="sxs-lookup"><span data-stu-id="64ab7-108">The process consists of two parts:</span></span>
1. <span data-ttu-id="64ab7-109">uppdatera dina befintliga Q #-filer och-projekt för att justera koden med en uppdaterad syntax</span><span class="sxs-lookup"><span data-stu-id="64ab7-109">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="64ab7-110">uppdatera själva QDK för din valda utvecklings miljö</span><span class="sxs-lookup"><span data-stu-id="64ab7-110">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="64ab7-111">Uppdaterar Q # projekt</span><span class="sxs-lookup"><span data-stu-id="64ab7-111">Updating Q# Projects</span></span> 

<span data-ttu-id="64ab7-112">Följ dessa anvisningar om du vill uppdatera C# dina q #-projekt oavsett om du använder eller python för att vara värd för q #-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="64ab7-112">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="64ab7-113">Kontrol lera först att du har den senaste versionen av [.NET Core SDK 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="64ab7-113">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="64ab7-114">Kör följande kommando i kommando tolken:</span><span class="sxs-lookup"><span data-stu-id="64ab7-114">Run the following command in the command prompt:</span></span>
    ```bash
    dotnet --version
    ```
<span data-ttu-id="64ab7-115">Kontrol lera att utdata är `3.1.100` eller högre.</span><span class="sxs-lookup"><span data-stu-id="64ab7-115">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="64ab7-116">Om inte, installerar du den [senaste versionen](https://dotnet.microsoft.com/download) och kontrollerar igen.</span><span class="sxs-lookup"><span data-stu-id="64ab7-116">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="64ab7-117">Följ sedan anvisningarna nedan beroende på dina inställningar (Visual Studio, Visual Studio Code eller direkt på kommando raden).</span><span class="sxs-lookup"><span data-stu-id="64ab7-117">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="64ab7-118">Uppdatera Q #-projekt i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="64ab7-118">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="64ab7-119">Uppdatera till den senaste versionen av Visual Studio 2019 finns [här](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) för instruktioner</span><span class="sxs-lookup"><span data-stu-id="64ab7-119">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="64ab7-120">Öppna din lösning i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="64ab7-120">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="64ab7-121">På menyn väljer du **Build** -> **ren lösning**</span><span class="sxs-lookup"><span data-stu-id="64ab7-121">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="64ab7-122">I var och en av dina. CSPROJ-filer uppdaterar du mål ramverket till `netcoreapp3.0` (eller `netstandard2.1` om det är ett biblioteks projekt).</span><span class="sxs-lookup"><span data-stu-id="64ab7-122">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="64ab7-123">Det vill säga Redigera rader i formuläret:</span><span class="sxs-lookup"><span data-stu-id="64ab7-123">That is, edit lines of the form:</span></span>
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    <span data-ttu-id="64ab7-124">Du hittar mer information om att ange mål ramverk [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="64ab7-124">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="64ab7-125">Spara och Stäng alla filer i lösningen</span><span class="sxs-lookup"><span data-stu-id="64ab7-125">Save and close all files in your solution</span></span>
6. <span data-ttu-id="64ab7-126">Välj **verktyg** -> **kommando rad** -> **Developer kommando tolken**</span><span class="sxs-lookup"><span data-stu-id="64ab7-126">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="64ab7-127">Kör följande kommando för varje projekt i lösningen:</span><span class="sxs-lookup"><span data-stu-id="64ab7-127">For each project in the solution, run the following command:</span></span>
    ```bash
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```
    <span data-ttu-id="64ab7-128">Om dina projekt använder andra Microsoft. Quantum-paket (t. ex. Microsoft. Quantum. numeric) kör du kommandot för dessa.</span><span class="sxs-lookup"><span data-stu-id="64ab7-128">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="64ab7-129">Stäng kommando tolken och välj **build** -> **build-lösning** (Välj *inte* att återskapa lösningen, eftersom återställningen kommer att Miss Förslut ATS)</span><span class="sxs-lookup"><span data-stu-id="64ab7-129">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

<span data-ttu-id="64ab7-130">Nu kan du gå vidare till [Uppdatera ditt Visual Studio QDK-tillägg](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="64ab7-130">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="64ab7-131">Uppdatera Q #-projekt i Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="64ab7-131">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="64ab7-132">Öppna mappen som innehåller projektet som ska uppdateras i Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="64ab7-132">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="64ab7-133">Välj **terminal** -> **ny terminal**</span><span class="sxs-lookup"><span data-stu-id="64ab7-133">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="64ab7-134">Följ anvisningarna för uppdatering med hjälp av kommando raden (direkt nedan)</span><span class="sxs-lookup"><span data-stu-id="64ab7-134">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="64ab7-135">Uppdatera Q #-projekt med hjälp av kommando raden</span><span class="sxs-lookup"><span data-stu-id="64ab7-135">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="64ab7-136">Navigera till mappen som innehåller projekt filen</span><span class="sxs-lookup"><span data-stu-id="64ab7-136">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="64ab7-137">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="64ab7-137">Run the following command:</span></span>
    ```bash
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="64ab7-138">I var och en av dina. CSPROJ-filer uppdaterar du mål ramverket till `netcoreapp3.0` (eller `netstandard2.1` om det är ett biblioteks projekt).</span><span class="sxs-lookup"><span data-stu-id="64ab7-138">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="64ab7-139">Det vill säga Redigera rader i formuläret:</span><span class="sxs-lookup"><span data-stu-id="64ab7-139">That is, edit lines of the form:</span></span>
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    <span data-ttu-id="64ab7-140">Du hittar mer information om att ange mål ramverk [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="64ab7-140">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="64ab7-141">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="64ab7-141">Run the following command:</span></span>
    ```bash
    dotnet add package Microsoft.Quantum.Development.Kit
    ```
    <span data-ttu-id="64ab7-142">Om projektet använder andra Microsoft. Quantum-paket (t. ex. Microsoft. Quantum. numeric) kör du kommandot för dessa.</span><span class="sxs-lookup"><span data-stu-id="64ab7-142">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="64ab7-143">Spara och Stäng alla filer.</span><span class="sxs-lookup"><span data-stu-id="64ab7-143">Save and close all files.</span></span>
6. <span data-ttu-id="64ab7-144">Upprepa 1-4 för varje projekt beroende och gå sedan tillbaka till mappen som innehåller huvud projektet och kör:</span><span class="sxs-lookup"><span data-stu-id="64ab7-144">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
    ```bash
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="64ab7-145">När du har uppdaterat dina Q #-projekt följer du anvisningarna nedan för att uppdatera själva QDK.</span><span class="sxs-lookup"><span data-stu-id="64ab7-145">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="64ab7-146">Uppdaterar QDK</span><span class="sxs-lookup"><span data-stu-id="64ab7-146">Updating the QDK</span></span>

<span data-ttu-id="64ab7-147">Processen för att uppdatera QDK varierar beroende på ditt utvecklings språk och miljö.</span><span class="sxs-lookup"><span data-stu-id="64ab7-147">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="64ab7-148">Välj din utvecklings miljö nedan.</span><span class="sxs-lookup"><span data-stu-id="64ab7-148">Select your development environment below.</span></span>

* [<span data-ttu-id="64ab7-149">Python: uppdatera SWEETIQ #-tillägget</span><span class="sxs-lookup"><span data-stu-id="64ab7-149">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="64ab7-150">Jupyter Notebook: uppdatera SWEETIQ #-tillägget</span><span class="sxs-lookup"><span data-stu-id="64ab7-150">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="64ab7-151">Visual Studio: uppdatera tillägget QDK</span><span class="sxs-lookup"><span data-stu-id="64ab7-151">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="64ab7-152">VS Code: uppdatera tillägget QDK</span><span class="sxs-lookup"><span data-stu-id="64ab7-152">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="64ab7-153">Kommando rad och C#: uppdatera projektmallar</span><span class="sxs-lookup"><span data-stu-id="64ab7-153">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="64ab7-154">Uppdatera SWEETIQ # för python</span><span class="sxs-lookup"><span data-stu-id="64ab7-154">Update IQ# for Python</span></span>

1. <span data-ttu-id="64ab7-155">Uppdatera `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="64ab7-155">Update the `iqsharp` kernel</span></span> 

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="64ab7-156">Verifiera `iqsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="64ab7-156">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="64ab7-157">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="64ab7-157">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```
    <span data-ttu-id="64ab7-158">Oroa dig inte om din `iqsharp` version är högre, bör den matcha den [senaste versionen](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="64ab7-158">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="64ab7-159">Uppdatera `qsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="64ab7-159">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="64ab7-160">Verifiera `qsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="64ab7-160">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="64ab7-161">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="64ab7-161">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
5. <span data-ttu-id="64ab7-162">Kör följande kommando från platsen för dina `.qs`-filer</span><span class="sxs-lookup"><span data-stu-id="64ab7-162">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="64ab7-163">Nu kan du använda den uppdaterade QDK-versionen för att köra befintliga Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="64ab7-163">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="64ab7-164">Uppdatera SWEETIQ # för Jupyter-anteckningsböcker</span><span class="sxs-lookup"><span data-stu-id="64ab7-164">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="64ab7-165">Uppdatera `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="64ab7-165">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="64ab7-166">Verifiera `iqsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="64ab7-166">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="64ab7-167">Dina utdata bör likna följande:</span><span class="sxs-lookup"><span data-stu-id="64ab7-167">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```
    <span data-ttu-id="64ab7-168">Oroa dig inte om din `iqsharp` version är högre, bör den matcha den [senaste versionen](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="64ab7-168">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="64ab7-169">Kör följande kommando från en cell i Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="64ab7-169">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

4. <span data-ttu-id="64ab7-170">Nu kan du öppna en befintlig Jupyter-anteckningsbok och köra den med den uppdaterade QDK.</span><span class="sxs-lookup"><span data-stu-id="64ab7-170">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="64ab7-171">Uppdatera Visual Studio QDK-tillägg</span><span class="sxs-lookup"><span data-stu-id="64ab7-171">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="64ab7-172">Uppdatera Q # Visual Studio-tillägget</span><span class="sxs-lookup"><span data-stu-id="64ab7-172">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="64ab7-173">Visual Studio efterfrågar att du accepterar uppdateringar av [Quantum Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="64ab7-173">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="64ab7-174">Godkänn uppdateringen</span><span class="sxs-lookup"><span data-stu-id="64ab7-174">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="64ab7-175">Projektfilerna uppdateras med tillägget.</span><span class="sxs-lookup"><span data-stu-id="64ab7-175">The project templates are updated with the extension.</span></span> <span data-ttu-id="64ab7-176">De uppdaterade mallarna gäller endast för nyligen skapade projekt.</span><span class="sxs-lookup"><span data-stu-id="64ab7-176">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="64ab7-177">Koden för dina befintliga projekt uppdateras inte när tillägget uppdateras.</span><span class="sxs-lookup"><span data-stu-id="64ab7-177">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="64ab7-178">Uppdatera VS Code QDK-tillägg</span><span class="sxs-lookup"><span data-stu-id="64ab7-178">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="64ab7-179">Uppdatera tillägget för Quantum VS Code</span><span class="sxs-lookup"><span data-stu-id="64ab7-179">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="64ab7-180">Starta om VS-kod</span><span class="sxs-lookup"><span data-stu-id="64ab7-180">Restart VS Code</span></span>
    - <span data-ttu-id="64ab7-181">Navigera till fliken **tillägg**</span><span class="sxs-lookup"><span data-stu-id="64ab7-181">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="64ab7-182">Välj **Microsoft Quantum Development Kit för Visual Studio Code** -tillägg</span><span class="sxs-lookup"><span data-stu-id="64ab7-182">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="64ab7-183">Läs in tillägget igen</span><span class="sxs-lookup"><span data-stu-id="64ab7-183">Reload the extension</span></span>

2. <span data-ttu-id="64ab7-184">Uppdatera Quantum-projektmallar:</span><span class="sxs-lookup"><span data-stu-id="64ab7-184">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="64ab7-185">Gå till **Visa** -> **Kommandopaletten**</span><span class="sxs-lookup"><span data-stu-id="64ab7-185">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="64ab7-186">Välj **Q #: installera projektmallar**</span><span class="sxs-lookup"><span data-stu-id="64ab7-186">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="64ab7-187">Efter några sekunder bör du få ett popup-meddelande om att Project-mallar har installerats</span><span class="sxs-lookup"><span data-stu-id="64ab7-187">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="64ab7-188">C#, med hjälp av kommando rads verktyget `dotnet`</span><span class="sxs-lookup"><span data-stu-id="64ab7-188">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="64ab7-189">Uppdatera Quantum Project-mallar för .NET</span><span class="sxs-lookup"><span data-stu-id="64ab7-189">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="64ab7-190">Vad står på tur?</span><span class="sxs-lookup"><span data-stu-id="64ab7-190">What's next?</span></span>

<span data-ttu-id="64ab7-191">Nu när du har uppdaterat Quantum Development Kit i din önskade miljö kan du fortsätta att utveckla och köra dina Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="64ab7-191">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="64ab7-192">Om du inte har skrivit ett program ännu kan du komma igång med [ditt första Quantum-program](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="64ab7-192">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
