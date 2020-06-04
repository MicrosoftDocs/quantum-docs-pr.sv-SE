---
title: Uppdatera Quantum Development Kit (QDK)
description: 'Beskriver hur du uppdaterar dina Q #-projekt och Microsoft Quantum Development Kit till den aktuella versionen.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 3245f587493ce12cfec15c8f932fd092d85f688e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327584"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="7ffd0-103">Uppdatera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="7ffd0-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="7ffd0-104">Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK) till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="7ffd0-105">Den här artikeln förutsätter att du redan har installerat QDK.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="7ffd0-106">Om du installerar för första gången kan du läsa [installations guiden](xref:microsoft.quantum.install)för.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="7ffd0-107">Vi rekommenderar att du håller dig uppdaterad med den senaste versionen av QDK.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="7ffd0-108">Följ den här uppdaterings guiden för att uppgradera till den senaste versionen av QDK.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="7ffd0-109">Processen består av två delar:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="7ffd0-110">Uppdatera dina befintliga Q #-filer och-projekt för att justera koden med en uppdaterad syntax.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="7ffd0-111">Uppdatera själva QDK för din valda utvecklings miljö.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="7ffd0-112">Uppdaterar Q # projekt</span><span class="sxs-lookup"><span data-stu-id="7ffd0-112">Updating Q# Projects</span></span> 

<span data-ttu-id="7ffd0-113">Följ dessa anvisningar om du vill uppdatera dina Q #-projekt oavsett om du använder C# eller python som värd för Q #-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="7ffd0-114">Kontrol lera först att du har den senaste versionen av [.NET Core SDK 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="7ffd0-115">Kör följande kommando i kommando tolken:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="7ffd0-116">Kontrol lera att utdata är `3.1.100` eller högre.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="7ffd0-117">Om inte, installerar du den [senaste versionen](https://dotnet.microsoft.com/download) och kontrollerar igen.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="7ffd0-118">Följ sedan anvisningarna nedan beroende på dina inställningar (Visual Studio, Visual Studio Code eller direkt på kommando raden).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="7ffd0-119">Uppdatera Q #-projekt i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7ffd0-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="7ffd0-120">Uppdatera till den senaste versionen av Visual Studio 2019, finns [här](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="7ffd0-121">Öppna din lösning i Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="7ffd0-122">Välj **Bygg**  ->  **ren lösning**på menyn.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="7ffd0-123">I var och en av dina. CSPROJ-filer uppdaterar du mål ramverket till `netcoreapp3.1` (eller `netstandard2.1` om det är ett biblioteks projekt).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="7ffd0-124">Det vill säga Redigera rader i formuläret:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="7ffd0-125">Du hittar mer information om att ange mål ramverk [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="7ffd0-126">I var och en av CSPROJ-filerna ställer du in SDK till `Microsoft.Quantum.Sdk` , som anges i raden nedan.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="7ffd0-127">Observera att versions numret måste vara det senaste tillgängliga och du kan fastställa det genom att granska [versions anteckningarna](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="7ffd0-128">Spara och Stäng alla filer i lösningen.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="7ffd0-129">Välj **verktyg**  ->  **kommando rad**  ->  **utvecklare kommando tolk**.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="7ffd0-130">Du kan också använda paket hanterings konsolen i Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="7ffd0-131">För varje projekt i lösningen kör du följande kommando för att **ta bort** det här paketet:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="7ffd0-132">Om dina projekt använder andra Microsoft. Quantum-eller Microsoft. Azure. Quantum-paket (t. ex. Microsoft. Quantum. numeric) kör du kommandot **Add** för att uppdatera den version som används.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="7ffd0-133">Stäng kommando tolken och välj **skapa**  ->  **build-lösning** (Välj *inte* att återskapa lösningen).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="7ffd0-134">Nu kan du gå vidare till [Uppdatera ditt Visual Studio QDK-tillägg](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="7ffd0-135">Uppdatera Q #-projekt i Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7ffd0-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="7ffd0-136">Öppna mappen som innehåller projektet som ska uppdateras i Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="7ffd0-137">Välj **Terminal**-  ->  **ny terminal**.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="7ffd0-138">Följ anvisningarna för uppdatering med hjälp av kommando raden (direkt nedan).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="7ffd0-139">Uppdatera Q #-projekt med hjälp av kommando raden</span><span class="sxs-lookup"><span data-stu-id="7ffd0-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="7ffd0-140">Navigera till mappen som innehåller huvud projekt filen.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="7ffd0-141">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="7ffd0-142">Bestäm den aktuella versionen av QDK.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="7ffd0-143">För att hitta det kan du läsa [viktig information](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="7ffd0-144">Versionen är i ett format som liknar `0.11.2006.207` .</span><span class="sxs-lookup"><span data-stu-id="7ffd0-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="7ffd0-145">I var och en av dina `.csproj` filer går du igenom följande steg:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="7ffd0-146">Uppdatera mål ramverket till `netcoreapp3.1` (eller `netstandard2.1` om det är ett biblioteks projekt).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="7ffd0-147">Det vill säga Redigera rader i formuläret:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="7ffd0-148">Du hittar mer information om att ange mål ramverk [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="7ffd0-149">Ersätt referensen till SDK i projekt definitionen.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="7ffd0-150">Kontrol lera att versions numret motsvarar det värde som fastställs i **steg 3**.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="7ffd0-151">Ta bort referensen till paketet `Microsoft.Quantum.Development.Kit` , om den finns, som ska anges i följande post:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="7ffd0-152">Uppdatera versionen av alla Microsoft Quantum-paket till den senast utgivna versionen av QDK (som fastställs i **steg 3**).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="7ffd0-153">Dessa paket namnges med följande mönster:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="7ffd0-154">Referenser till paket har följande format:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="7ffd0-155">Spara den uppdaterade filen.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-155">Save the updated file.</span></span>

    - <span data-ttu-id="7ffd0-156">Återställ projektets beroenden genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="7ffd0-157">Navigera tillbaka till mappen som innehåller huvud projektet och kör:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="7ffd0-158">När du har uppdaterat dina Q #-projekt följer du anvisningarna nedan för att uppdatera själva QDK.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="7ffd0-159">Uppdaterar QDK</span><span class="sxs-lookup"><span data-stu-id="7ffd0-159">Updating the QDK</span></span>

<span data-ttu-id="7ffd0-160">Processen för att uppdatera QDK varierar beroende på ditt utvecklings språk och miljö.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="7ffd0-161">Välj din utvecklings miljö nedan.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-161">Select your development environment below.</span></span>

* [<span data-ttu-id="7ffd0-162">Python: uppdatera SWEETIQ #-tillägget</span><span class="sxs-lookup"><span data-stu-id="7ffd0-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="7ffd0-163">Jupyter Notebook: uppdatera SWEETIQ #-tillägget</span><span class="sxs-lookup"><span data-stu-id="7ffd0-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="7ffd0-164">Visual Studio: uppdatera tillägget QDK</span><span class="sxs-lookup"><span data-stu-id="7ffd0-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="7ffd0-165">VS Code: uppdatera tillägget QDK</span><span class="sxs-lookup"><span data-stu-id="7ffd0-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="7ffd0-166">Kommando rad och C#: uppdatera projektmallar</span><span class="sxs-lookup"><span data-stu-id="7ffd0-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="7ffd0-167">Uppdatera SWEETIQ # för python</span><span class="sxs-lookup"><span data-stu-id="7ffd0-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="7ffd0-168">Uppdatera `iqsharp` kerneln</span><span class="sxs-lookup"><span data-stu-id="7ffd0-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="7ffd0-169">Verifiera `iqsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="7ffd0-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="7ffd0-170">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-170">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="7ffd0-171">Oroa dig inte om din `iqsharp` version är högre, den ska överensstämma med den [senaste versionen](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="7ffd0-172">Uppdatera `qsharp` paketet</span><span class="sxs-lookup"><span data-stu-id="7ffd0-172">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="7ffd0-173">Verifiera `qsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="7ffd0-173">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="7ffd0-174">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-174">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="7ffd0-175">Kör följande kommando från platsen för dina `.qs` filer</span><span class="sxs-lookup"><span data-stu-id="7ffd0-175">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="7ffd0-176">Nu kan du använda den uppdaterade QDK-versionen för att köra befintliga Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="7ffd0-177">Uppdatera SWEETIQ # för Jupyter-anteckningsböcker</span><span class="sxs-lookup"><span data-stu-id="7ffd0-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="7ffd0-178">Uppdatera `iqsharp` kerneln</span><span class="sxs-lookup"><span data-stu-id="7ffd0-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="7ffd0-179">Verifiera `iqsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="7ffd0-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="7ffd0-180">Dina utdata bör likna följande:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-180">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="7ffd0-181">Oroa dig inte om din `iqsharp` version är högre, den ska överensstämma med den [senaste versionen](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="7ffd0-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="7ffd0-182">Kör följande kommando från en cell i Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="7ffd0-183">Nu kan du öppna en befintlig Jupyter-anteckningsbok och köra den med den uppdaterade QDK.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="7ffd0-184">Uppdatera Visual Studio QDK-tillägg</span><span class="sxs-lookup"><span data-stu-id="7ffd0-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="7ffd0-185">Uppdatera Q # Visual Studio-tillägget</span><span class="sxs-lookup"><span data-stu-id="7ffd0-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="7ffd0-186">Visual Studio efterfrågar att du accepterar uppdateringar av [Quantum Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="7ffd0-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="7ffd0-187">Godkänn uppdateringen</span><span class="sxs-lookup"><span data-stu-id="7ffd0-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="7ffd0-188">Projektfilerna uppdateras med tillägget.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="7ffd0-189">De uppdaterade mallarna gäller endast för nyligen skapade projekt.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="7ffd0-190">Koden för dina befintliga projekt uppdateras inte när tillägget uppdateras.</span><span class="sxs-lookup"><span data-stu-id="7ffd0-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="7ffd0-191">Uppdatera VS Code QDK-tillägg</span><span class="sxs-lookup"><span data-stu-id="7ffd0-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="7ffd0-192">Uppdatera tillägget för Quantum VS Code</span><span class="sxs-lookup"><span data-stu-id="7ffd0-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="7ffd0-193">Starta om VS-kod</span><span class="sxs-lookup"><span data-stu-id="7ffd0-193">Restart VS Code</span></span>
    - <span data-ttu-id="7ffd0-194">Navigera till fliken **tillägg**</span><span class="sxs-lookup"><span data-stu-id="7ffd0-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="7ffd0-195">Välj **Microsoft Quantum Development Kit för Visual Studio Code** -tillägg</span><span class="sxs-lookup"><span data-stu-id="7ffd0-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="7ffd0-196">Läs in tillägget igen</span><span class="sxs-lookup"><span data-stu-id="7ffd0-196">Reload the extension</span></span>

2. <span data-ttu-id="7ffd0-197">Uppdatera Quantum-projektmallar:</span><span class="sxs-lookup"><span data-stu-id="7ffd0-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="7ffd0-198">Gå till **Visa**  ->  **kommando palett**</span><span class="sxs-lookup"><span data-stu-id="7ffd0-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="7ffd0-199">Välj **Q #: installera projektmallar**</span><span class="sxs-lookup"><span data-stu-id="7ffd0-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="7ffd0-200">Efter några sekunder bör du få ett popup-meddelande om att Project-mallar har installerats</span><span class="sxs-lookup"><span data-stu-id="7ffd0-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="7ffd0-201">C# med `dotnet` kommando rads verktyget</span><span class="sxs-lookup"><span data-stu-id="7ffd0-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="7ffd0-202">Uppdatera Quantum Project-mallar för .NET</span><span class="sxs-lookup"><span data-stu-id="7ffd0-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
