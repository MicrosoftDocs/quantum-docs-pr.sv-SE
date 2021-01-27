---
title: Uppdatera Quantum Development Kit (QDK)
description: Beskriver hur du uppdaterar Q#-projekt och Microsoft Quantum Development Kit till den aktuella versionen.
author: bradben
ms.author: v-benbra
ms.date: 5/30/2020
ms.topic: quickstart
uid: microsoft.quantum.update
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1b5def3226bd073c878f8573aaddd757d733ec48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858051"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="3a4dc-103">Uppdatera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="3a4dc-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="3a4dc-104">Lär dig att uppdatera Microsoft Quantum Development Kit till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="3a4dc-105">Den här artikeln förutsätter att du redan har installerat QDK.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="3a4dc-106">Om du installerar för första gången kan du läsa [installationsguiden](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="3a4dc-107">Vi rekommenderar att har den senaste QDK-versionen.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="3a4dc-108">Följ den här uppdateringsguiden för att uppgradera till den senaste QDK-versionen.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="3a4dc-109">Processen består av två delar:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="3a4dc-110">Uppdatera dina befintliga Q#-filer och projekt för att justera koden med en uppdaterad syntax.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="3a4dc-111">Uppdatera själva QDK:n för din valda utvecklingsmiljö.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-no-locq-projects"></a><span data-ttu-id="3a4dc-112">Uppdatera Q#-projekt</span><span class="sxs-lookup"><span data-stu-id="3a4dc-112">Updating Q# Projects</span></span> 

<span data-ttu-id="3a4dc-113">Oavsett om du använder C# eller Python för att värdhantera Q#-åtgärder följer du dessa instruktioner för att uppdatera dina Q#-projekt.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="3a4dc-114">Kontrollera först att du har den senaste versionen av [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="3a4dc-115">Kör följande kommando i kommandotolken:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="3a4dc-116">Kontrollera att utdatan är `3.1.100` eller högre.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="3a4dc-117">Om inte, installerar du den [senaste versionen](https://dotnet.microsoft.com/download) och kontrollerar igen.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="3a4dc-118">Följ sedan anvisningarna nedan beroende på din konfiguration (Visual Studio, Visual Studio Code eller direkt från kommandotolken).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly from the command prompt).</span></span>

### <a name="update-no-locq-projects-in-visual-studio"></a><span data-ttu-id="3a4dc-119">Uppdatera Q#-projekt i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3a4dc-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="3a4dc-120">Uppdatera till den senaste versionen av Visual Studio 2019. Mer information finns [här](https://docs.microsoft.com/visualstudio/install/update-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio) for instructions.</span></span>
2. <span data-ttu-id="3a4dc-121">Öppna därefter lösningen i Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="3a4dc-122">I menyn väljer du **Version** -> **Rensa lösning**.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="3a4dc-123">I varje .csproj-fil uppdaterar du målramverket till `netcoreapp3.1` (eller `netstandard2.1` om det är ett biblioteksprojekt).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="3a4dc-124">Det innebär att redigera rader i formuläret:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="3a4dc-125">Mer information om att ange målramverk finns [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="3a4dc-126">I var och en av .csproj-filerna ställer du in SDK:n på `Microsoft.Quantum.Sdk`, enligt raden nedan.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="3a4dc-127">Observera att versionsnumret måste vara det senaste tillgängliga. Du hittar det i [Viktig information](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    ```

6. <span data-ttu-id="3a4dc-128">Spara och stäng alla filer i lösningen.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="3a4dc-129">Välj **Verktyg** -> **Kommandorad** -> **Kommandotolk för utvecklare**.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="3a4dc-130">Du kan också använda pakethanteringskonsolen i Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="3a4dc-131">Kör följande kommando för att **ta bort** paketet från alla projekt i lösningen:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="3a4dc-132">Om dina projekt använder andra Microsoft.Quantum- eller Microsoft.Azure.Quantum-paket (t.ex. Microsoft.Quantum.Numerics), kör du kommandot **Lägg till** för att uppdatera den version som används.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="3a4dc-133">Stäng kommandotolken och välj **Version** -> **Skapa lösning** (välj *inte* Återskapa lösning).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="3a4dc-134">Nu kan du gå vidare med att [uppdatera ditt Visual Studio QDK-tillägg](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-no-locq-projects-in-visual-studio-code"></a><span data-ttu-id="3a4dc-135">Uppdatera Q#-projekt i Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3a4dc-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="3a4dc-136">I Visual Studio Code öppnar du mappen med projektet som ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="3a4dc-137">Välj **Terminal** -> **Ny terminal**.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="3a4dc-138">Följ anvisningarna för uppdatering med kommandotolken (visas nedan).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-138">Follow the instructions for updating using the command prompt (directly below).</span></span>

### <a name="update-no-locq-projects-using-the-command-prompt"></a><span data-ttu-id="3a4dc-139">Uppdatera Q#-projekt med kommandotolken</span><span class="sxs-lookup"><span data-stu-id="3a4dc-139">Update Q# projects using the command prompt</span></span>

1. <span data-ttu-id="3a4dc-140">Gå till mappen med huvudprojektfilen.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="3a4dc-141">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="3a4dc-142">Fastställ den aktuella QDK-versionen.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="3a4dc-143">För att hitta den kan du läsa [Viktig information](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="3a4dc-144">Versionen är i ett format som liknar `0.12.20072031`.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-144">The version will be in a format similar to `0.12.20072031`.</span></span>

4. <span data-ttu-id="3a4dc-145">Gå igenom följande steg för alla dina `.csproj`-filer:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="3a4dc-146">Uppdatera målramverket till `netcoreapp3.1` (eller `netstandard2.1` om det är ett biblioteksprojekt).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="3a4dc-147">Det innebär att redigera rader i formuläret:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="3a4dc-148">Mer information om att ange målramverk finns [här](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="3a4dc-149">Ersätt referensen till SDK:n i projektdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="3a4dc-150">Kontrollera att versionsnumret motsvarar det värde som fastställdes i **steg 3**.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
        ```

    - <span data-ttu-id="3a4dc-151">Ta bort referensen till paket `Microsoft.Quantum.Development.Kit`, om ett sådant finns, vilket anges i följande post:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="3a4dc-152">Uppdatera versionen av alla Microsoft Quantum-paket till den senast utgivna versionen av QDK:n (fastställs i **steg 3**).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="3a4dc-153">Dessa paket namnges enligt följande mönster:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="3a4dc-154">Referenser till paket har följande format:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
        ```

    - <span data-ttu-id="3a4dc-155">Spara den uppdaterade filen.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-155">Save the updated file.</span></span>

    - <span data-ttu-id="3a4dc-156">Återställ projektets beroenden genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="3a4dc-157">Gå tillbaka till mappen med huvudprojektet och kör:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="3a4dc-158">Nu när du har uppdaterat dina Q#-projekt följer du anvisningarna nedan för att uppdatera själva QDK:n.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="3a4dc-159">Uppdaterar QDK:n</span><span class="sxs-lookup"><span data-stu-id="3a4dc-159">Updating the QDK</span></span>

<span data-ttu-id="3a4dc-160">Processen för att uppdatera QDK:n varierar beroende på utvecklingsspråk och miljö.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="3a4dc-161">Välj din utvecklingsmiljö nedan.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-161">Select your development environment below.</span></span>

* [<span data-ttu-id="3a4dc-162">Python: uppdatera `qsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="3a4dc-162">Python: update the `qsharp` package</span></span>](#update-the-qsharp-python-package)
* [<span data-ttu-id="3a4dc-163">Jupyter Notebooks: uppdatera IQ#-kärnan</span><span class="sxs-lookup"><span data-stu-id="3a4dc-163">Jupyter Notebooks: update the IQ# kernel</span></span>](#update-the-iq-jupyter-kernel)
* [<span data-ttu-id="3a4dc-164">Visual Studio: Uppdatera QDK-tillägget</span><span class="sxs-lookup"><span data-stu-id="3a4dc-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="3a4dc-165">VS Code: Uppdatera QDK-tillägget</span><span class="sxs-lookup"><span data-stu-id="3a4dc-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="3a4dc-166">Kommandorad och C#: Uppdatera projektmallar</span><span class="sxs-lookup"><span data-stu-id="3a4dc-166">Command line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a><span data-ttu-id="3a4dc-167">Uppdatera Python-paketet `qsharp`</span><span class="sxs-lookup"><span data-stu-id="3a4dc-167">Update the `qsharp` Python package</span></span>

<span data-ttu-id="3a4dc-168">Uppdateringsproceduren beror på om du ursprungligen installerade med hjälp av conda eller med .NET CLI och pip.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-168">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="3a4dc-169">Uppdatera med hjälp av conda (rekommenderas)</span><span class="sxs-lookup"><span data-stu-id="3a4dc-169">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="3a4dc-170">Aktivera den conda-miljö där du installerade `qsharp`-paketet och kör sedan det här kommandot för att uppdatera det:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-170">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="3a4dc-171">Kör följande kommando från platsen för dina `.qs`-filer:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-171">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="3a4dc-172">Uppdatera med hjälp av .NET CLI och pip (avancerat)</span><span class="sxs-lookup"><span data-stu-id="3a4dc-172">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="3a4dc-173">Uppdatera din `iqsharp`-kernel</span><span class="sxs-lookup"><span data-stu-id="3a4dc-173">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="3a4dc-174">Kontrollera `iqsharp`-versionen</span><span class="sxs-lookup"><span data-stu-id="3a4dc-174">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="3a4dc-175">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-175">You should see the following output:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="3a4dc-176">Oroa dig inte om din `iqsharp`-version är högre.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-176">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="3a4dc-177">Den ska överensstämma med den [senaste versionen](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-177">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="3a4dc-178">Uppdatera `qsharp`-paketet:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-178">Update the `qsharp` package:</span></span>

    ```
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="3a4dc-179">Kontrollera `qsharp`-versionen:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-179">Verify the `qsharp` version:</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="3a4dc-180">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-180">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="3a4dc-181">Kör följande kommando från platsen för dina `.qs`-filer:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-181">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

<span data-ttu-id="3a4dc-182">Nu kan du använda det uppdaterade Python-paketet `qsharp` till att köra befintliga kvantprogram.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-182">You can now use the updated `qsharp` Python package to run your existing quantum programs.</span></span>

### <a name="update-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="3a4dc-183">Uppdatera IQ# Jupyter-kärnan</span><span class="sxs-lookup"><span data-stu-id="3a4dc-183">Update the IQ# Jupyter kernel</span></span>

<span data-ttu-id="3a4dc-184">Uppdateringsproceduren beror på om du ursprungligen installerade med hjälp av conda eller med .NET CLI och pip.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-184">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="3a4dc-185">Uppdatera med hjälp av conda (rekommenderas)</span><span class="sxs-lookup"><span data-stu-id="3a4dc-185">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="3a4dc-186">Aktivera den conda-miljö där du installerade `qsharp`-paketet och kör sedan det här kommandot för att uppdatera det:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-186">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="3a4dc-187">Kör följande kommando från en cell i var och en av dina befintliga Q#-Jupyter Notebooks:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-187">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="3a4dc-188">Uppdatera med hjälp av .NET CLI och pip (avancerat)</span><span class="sxs-lookup"><span data-stu-id="3a4dc-188">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="3a4dc-189">Uppdatera `Microsoft.Quantum.IQSharp`-paketet:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-189">Update the `Microsoft.Quantum.IQSharp` package:</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="3a4dc-190">Kontrollera `iqsharp`-versionen:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-190">Verify the `iqsharp` version:</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="3a4dc-191">Ditt resultat bör likna följande:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-191">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="3a4dc-192">Oroa dig inte om din `iqsharp`-version är högre.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-192">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="3a4dc-193">Den ska överensstämma med den [senaste versionen](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="3a4dc-193">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="3a4dc-194">Kör följande kommando från en cell i var och en av dina befintliga Q#-Jupyter Notebooks:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-194">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

<span data-ttu-id="3a4dc-195">\*\*_</span><span class="sxs-lookup"><span data-stu-id="3a4dc-195">\*\*_</span></span>

<span data-ttu-id="3a4dc-196">Nu kan du använda den uppdaterade IQ#-kärnan för att köra dina befintliga Q#-Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-196">You can now use the updated IQ# kernel to run your existing Q# Jupyter Notebooks.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="3a4dc-197">Uppdatera QDK-tillägg i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3a4dc-197">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="3a4dc-198">Uppdatera Visual Studio-tillägget för Q#</span><span class="sxs-lookup"><span data-stu-id="3a4dc-198">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="3a4dc-199">Visual Studio uppmanar dig att acceptera uppdateringar av [Quantum-tillägget för Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="3a4dc-199">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="3a4dc-200">Godkänn uppdateringen</span><span class="sxs-lookup"><span data-stu-id="3a4dc-200">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a4dc-201">Projektmallarna uppdateras med tillägget.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-201">The project templates are updated with the extension.</span></span> <span data-ttu-id="3a4dc-202">De uppdaterade mallarna gäller endast för nyligen skapade projekt.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-202">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="3a4dc-203">Koden i dina befintliga projekt uppdateras inte när tillägget uppdateras.</span><span class="sxs-lookup"><span data-stu-id="3a4dc-203">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="3a4dc-204">Uppdatera QDK-tillägg för VS Code</span><span class="sxs-lookup"><span data-stu-id="3a4dc-204">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="3a4dc-205">Uppdatera Quantum-tillägget för VS Code</span><span class="sxs-lookup"><span data-stu-id="3a4dc-205">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="3a4dc-206">Starta om VS Code</span><span class="sxs-lookup"><span data-stu-id="3a4dc-206">Restart VS Code</span></span>
    - <span data-ttu-id="3a4dc-207">Gå till fliken _ *tillägg*\*</span><span class="sxs-lookup"><span data-stu-id="3a4dc-207">Navigate to the _ *Extensions*\* tab</span></span>
    - <span data-ttu-id="3a4dc-208">Välj tillägget **Microsoft Quantum Development Kit för Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="3a4dc-208">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="3a4dc-209">Läs in tillägget på nytt</span><span class="sxs-lookup"><span data-stu-id="3a4dc-209">Reload the extension</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="3a4dc-210">C#, med hjälp av kommandoradsverktyget `dotnet`</span><span class="sxs-lookup"><span data-stu-id="3a4dc-210">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="3a4dc-211">Uppdatera Quantum-projektmallar för .NET</span><span class="sxs-lookup"><span data-stu-id="3a4dc-211">Update the Quantum project templates for .NET</span></span>

    <span data-ttu-id="3a4dc-212">I kommandotolken:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-212">From the command prompt:</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   <span data-ttu-id="3a4dc-213">Om du tänker använda kommandoradsmallarna och redan har installerat QDK-tillägget för VS Code kan du också uppdatera projektmallarna från själva tillägget:</span><span class="sxs-lookup"><span data-stu-id="3a4dc-213">Alternatively, if you intend to use the command-line templates, and already have the VS Code QDK extension installed, you can update the project templates from the extension itself:</span></span>

   - [<span data-ttu-id="3a4dc-214">Uppdatera QDK-tillägget</span><span class="sxs-lookup"><span data-stu-id="3a4dc-214">Update the QDK extension</span></span>](#update-vs-code-qdk-extension)
   - <span data-ttu-id="3a4dc-215">Gå till **Visa** -> **Kommandopaletten** i VS Code</span><span class="sxs-lookup"><span data-stu-id="3a4dc-215">In VS Code, go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="3a4dc-216">Välj **Q#: Installera projektmallar från kommandoraden**</span><span class="sxs-lookup"><span data-stu-id="3a4dc-216">Select **Q#: Install command line project templates**</span></span>
   - <span data-ttu-id="3a4dc-217">Efter några sekunder bör du få ett popup-meddelande som bekräftar att ”projektmallar har installerats”</span><span class="sxs-lookup"><span data-stu-id="3a4dc-217">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>
