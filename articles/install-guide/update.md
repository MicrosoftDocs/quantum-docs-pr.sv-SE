---
title: Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK)
description: 'Beskriver hur du uppdaterar dina Q #-projekt och Microsoft Quantum Development Kit till den aktuella versionen.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 264b5640216b2c0a468b625cdef4b9e0123d8b39
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904765"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="17d21-103">Uppdatera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="17d21-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="17d21-104">Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK) till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="17d21-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="17d21-105">Den här artikeln förutsätter att du redan har installerat QDK.</span><span class="sxs-lookup"><span data-stu-id="17d21-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="17d21-106">Om du installerar för första gången kan du läsa [installations guiden](xref:microsoft.quantum.install)för.</span><span class="sxs-lookup"><span data-stu-id="17d21-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="17d21-107">Vi rekommenderar att du håller dig uppdaterad med den senaste versionen av QDK.</span><span class="sxs-lookup"><span data-stu-id="17d21-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="17d21-108">Följ den här uppdaterings guiden för att uppgradera till den senaste versionen av QDK.</span><span class="sxs-lookup"><span data-stu-id="17d21-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="17d21-109">Processen består av två delar:</span><span class="sxs-lookup"><span data-stu-id="17d21-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="17d21-110">uppdatera dina befintliga Q #-filer och-projekt för att justera koden med en uppdaterad syntax</span><span class="sxs-lookup"><span data-stu-id="17d21-110">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="17d21-111">uppdatera själva QDK för din valda utvecklings miljö</span><span class="sxs-lookup"><span data-stu-id="17d21-111">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="17d21-112">Uppdaterar Q # projekt</span><span class="sxs-lookup"><span data-stu-id="17d21-112">Updating Q# Projects</span></span> 

<span data-ttu-id="17d21-113">Följ dessa anvisningar om du vill uppdatera C# dina q #-projekt oavsett om du använder eller python för att vara värd för q #-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="17d21-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="17d21-114">Kontrol lera först att du har den senaste versionen av [.NET Core SDK 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="17d21-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="17d21-115">Kör följande kommando i kommando tolken:</span><span class="sxs-lookup"><span data-stu-id="17d21-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="17d21-116">Kontrol lera att utdata är `3.1.100` eller högre.</span><span class="sxs-lookup"><span data-stu-id="17d21-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="17d21-117">Om inte, installerar du den [senaste versionen](https://dotnet.microsoft.com/download) och kontrollerar igen.</span><span class="sxs-lookup"><span data-stu-id="17d21-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="17d21-118">Följ sedan anvisningarna nedan beroende på dina inställningar (Visual Studio, Visual Studio Code eller direkt på kommando raden).</span><span class="sxs-lookup"><span data-stu-id="17d21-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="17d21-119">Uppdatera Q #-projekt i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="17d21-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="17d21-120">Uppdatera till den senaste versionen av Visual Studio 2019 finns [här](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) för instruktioner</span><span class="sxs-lookup"><span data-stu-id="17d21-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="17d21-121">Öppna din lösning i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="17d21-121">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="17d21-122">På menyn väljer du **Build** -> **ren lösning**</span><span class="sxs-lookup"><span data-stu-id="17d21-122">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="17d21-123">I var och en av dina. CSPROJ-filer uppdaterar du mål ramverket till `netcoreapp3.0` (eller `netstandard2.1` om det är ett biblioteks projekt).</span><span class="sxs-lookup"><span data-stu-id="17d21-123">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="17d21-124">Det vill säga Redigera rader i formuläret:</span><span class="sxs-lookup"><span data-stu-id="17d21-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="17d21-125">Du hittar mer information om att ange mål ramverk [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="17d21-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="17d21-126">Spara och Stäng alla filer i lösningen</span><span class="sxs-lookup"><span data-stu-id="17d21-126">Save and close all files in your solution</span></span>
6. <span data-ttu-id="17d21-127">Välj **verktyg** -> **kommando rad** -> **Developer kommando tolken**</span><span class="sxs-lookup"><span data-stu-id="17d21-127">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="17d21-128">Kör följande kommando för varje projekt i lösningen:</span><span class="sxs-lookup"><span data-stu-id="17d21-128">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="17d21-129">Om dina projekt använder andra Microsoft. Quantum-paket (t. ex. Microsoft. Quantum. numeric) kör du kommandot för dessa.</span><span class="sxs-lookup"><span data-stu-id="17d21-129">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="17d21-130">Stäng kommando tolken och välj **build** -> **build-lösning** (Välj *inte* att återskapa lösningen)</span><span class="sxs-lookup"><span data-stu-id="17d21-130">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="17d21-131">Nu kan du gå vidare till [Uppdatera ditt Visual Studio QDK-tillägg](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="17d21-131">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="17d21-132">Uppdatera Q #-projekt i Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="17d21-132">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="17d21-133">Öppna mappen som innehåller projektet som ska uppdateras i Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="17d21-133">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="17d21-134">Välj **terminal** -> **ny terminal**</span><span class="sxs-lookup"><span data-stu-id="17d21-134">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="17d21-135">Följ anvisningarna för uppdatering med hjälp av kommando raden (direkt nedan)</span><span class="sxs-lookup"><span data-stu-id="17d21-135">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="17d21-136">Uppdatera Q #-projekt med hjälp av kommando raden</span><span class="sxs-lookup"><span data-stu-id="17d21-136">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="17d21-137">Navigera till mappen som innehåller projekt filen</span><span class="sxs-lookup"><span data-stu-id="17d21-137">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="17d21-138">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="17d21-138">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="17d21-139">I var och en av dina. CSPROJ-filer uppdaterar du mål ramverket till `netcoreapp3.0` (eller `netstandard2.1` om det är ett biblioteks projekt).</span><span class="sxs-lookup"><span data-stu-id="17d21-139">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="17d21-140">Det vill säga Redigera rader i formuläret:</span><span class="sxs-lookup"><span data-stu-id="17d21-140">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="17d21-141">Du hittar mer information om att ange mål ramverk [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="17d21-141">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="17d21-142">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="17d21-142">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="17d21-143">Om projektet använder andra Microsoft. Quantum-paket (t. ex. Microsoft. Quantum. numeric) kör du kommandot för dessa.</span><span class="sxs-lookup"><span data-stu-id="17d21-143">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="17d21-144">Spara och Stäng alla filer.</span><span class="sxs-lookup"><span data-stu-id="17d21-144">Save and close all files.</span></span>
6. <span data-ttu-id="17d21-145">Upprepa 1-4 för varje projekt beroende och gå sedan tillbaka till mappen som innehåller huvud projektet och kör:</span><span class="sxs-lookup"><span data-stu-id="17d21-145">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="17d21-146">När du har uppdaterat dina Q #-projekt följer du anvisningarna nedan för att uppdatera själva QDK.</span><span class="sxs-lookup"><span data-stu-id="17d21-146">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="17d21-147">Uppdaterar QDK</span><span class="sxs-lookup"><span data-stu-id="17d21-147">Updating the QDK</span></span>

<span data-ttu-id="17d21-148">Processen för att uppdatera QDK varierar beroende på ditt utvecklings språk och miljö.</span><span class="sxs-lookup"><span data-stu-id="17d21-148">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="17d21-149">Välj din utvecklings miljö nedan.</span><span class="sxs-lookup"><span data-stu-id="17d21-149">Select your development environment below.</span></span>

* [<span data-ttu-id="17d21-150">Python: uppdatera SWEETIQ #-tillägget</span><span class="sxs-lookup"><span data-stu-id="17d21-150">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="17d21-151">Jupyter Notebook: uppdatera SWEETIQ #-tillägget</span><span class="sxs-lookup"><span data-stu-id="17d21-151">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="17d21-152">Visual Studio: uppdatera tillägget QDK</span><span class="sxs-lookup"><span data-stu-id="17d21-152">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="17d21-153">VS Code: uppdatera tillägget QDK</span><span class="sxs-lookup"><span data-stu-id="17d21-153">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="17d21-154">Kommando rad och C#: uppdatera projektmallar</span><span class="sxs-lookup"><span data-stu-id="17d21-154">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="17d21-155">Uppdatera SWEETIQ # för python</span><span class="sxs-lookup"><span data-stu-id="17d21-155">Update IQ# for Python</span></span>

1. <span data-ttu-id="17d21-156">Uppdatera `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="17d21-156">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="17d21-157">Verifiera `iqsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="17d21-157">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="17d21-158">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="17d21-158">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="17d21-159">Oroa dig inte om din `iqsharp` version är högre, bör den matcha den [senaste versionen](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="17d21-159">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="17d21-160">Uppdatera `qsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="17d21-160">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="17d21-161">Verifiera `qsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="17d21-161">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="17d21-162">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="17d21-162">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="17d21-163">Kör följande kommando från platsen för dina `.qs`-filer</span><span class="sxs-lookup"><span data-stu-id="17d21-163">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="17d21-164">Nu kan du använda den uppdaterade QDK-versionen för att köra befintliga Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="17d21-164">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="17d21-165">Uppdatera SWEETIQ # för Jupyter-anteckningsböcker</span><span class="sxs-lookup"><span data-stu-id="17d21-165">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="17d21-166">Uppdatera `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="17d21-166">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="17d21-167">Verifiera `iqsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="17d21-167">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="17d21-168">Dina utdata bör likna följande:</span><span class="sxs-lookup"><span data-stu-id="17d21-168">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="17d21-169">Oroa dig inte om din `iqsharp` version är högre, bör den matcha den [senaste versionen](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="17d21-169">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="17d21-170">Kör följande kommando från en cell i Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="17d21-170">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="17d21-171">Nu kan du öppna en befintlig Jupyter-anteckningsbok och köra den med den uppdaterade QDK.</span><span class="sxs-lookup"><span data-stu-id="17d21-171">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="17d21-172">Uppdatera Visual Studio QDK-tillägg</span><span class="sxs-lookup"><span data-stu-id="17d21-172">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="17d21-173">Uppdatera Q # Visual Studio-tillägget</span><span class="sxs-lookup"><span data-stu-id="17d21-173">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="17d21-174">Visual Studio efterfrågar att du accepterar uppdateringar av [Quantum Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="17d21-174">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="17d21-175">Godkänn uppdateringen</span><span class="sxs-lookup"><span data-stu-id="17d21-175">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="17d21-176">Projektfilerna uppdateras med tillägget.</span><span class="sxs-lookup"><span data-stu-id="17d21-176">The project templates are updated with the extension.</span></span> <span data-ttu-id="17d21-177">De uppdaterade mallarna gäller endast för nyligen skapade projekt.</span><span class="sxs-lookup"><span data-stu-id="17d21-177">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="17d21-178">Koden för dina befintliga projekt uppdateras inte när tillägget uppdateras.</span><span class="sxs-lookup"><span data-stu-id="17d21-178">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="17d21-179">Uppdatera VS Code QDK-tillägg</span><span class="sxs-lookup"><span data-stu-id="17d21-179">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="17d21-180">Uppdatera tillägget för Quantum VS Code</span><span class="sxs-lookup"><span data-stu-id="17d21-180">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="17d21-181">Starta om VS-kod</span><span class="sxs-lookup"><span data-stu-id="17d21-181">Restart VS Code</span></span>
    - <span data-ttu-id="17d21-182">Navigera till fliken **tillägg**</span><span class="sxs-lookup"><span data-stu-id="17d21-182">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="17d21-183">Välj **Microsoft Quantum Development Kit för Visual Studio Code** -tillägg</span><span class="sxs-lookup"><span data-stu-id="17d21-183">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="17d21-184">Läs in tillägget igen</span><span class="sxs-lookup"><span data-stu-id="17d21-184">Reload the extension</span></span>

2. <span data-ttu-id="17d21-185">Uppdatera Quantum-projektmallar:</span><span class="sxs-lookup"><span data-stu-id="17d21-185">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="17d21-186">Gå till **Visa** -> **Kommandopaletten**</span><span class="sxs-lookup"><span data-stu-id="17d21-186">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="17d21-187">Välj **Q #: installera projektmallar**</span><span class="sxs-lookup"><span data-stu-id="17d21-187">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="17d21-188">Efter några sekunder bör du få ett popup-meddelande om att Project-mallar har installerats</span><span class="sxs-lookup"><span data-stu-id="17d21-188">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="17d21-189">C#, med hjälp av kommando rads verktyget `dotnet`</span><span class="sxs-lookup"><span data-stu-id="17d21-189">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="17d21-190">Uppdatera Quantum Project-mallar för .NET</span><span class="sxs-lookup"><span data-stu-id="17d21-190">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="17d21-191">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="17d21-191">What's next?</span></span>

<span data-ttu-id="17d21-192">Nu när du har uppdaterat Quantum Development Kit i din önskade miljö kan du fortsätta att utveckla och köra dina Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="17d21-192">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="17d21-193">Om du inte har skrivit ett program ännu kan du komma igång med [ditt första Quantum-program](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="17d21-193">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
