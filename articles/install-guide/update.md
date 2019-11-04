---
title: Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463278"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="bfac9-102">Uppdatera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="bfac9-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="bfac9-103">Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK) till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="bfac9-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="bfac9-104">Den här artikeln förutsätter att du redan har installerat QDK.</span><span class="sxs-lookup"><span data-stu-id="bfac9-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="bfac9-105">Om du installerar för första gången kan du läsa [installations guiden](xref:microsoft.quantum.install)för.</span><span class="sxs-lookup"><span data-stu-id="bfac9-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>


## <a name="updating-q-projects"></a><span data-ttu-id="bfac9-106">Uppdaterar Q # projekt</span><span class="sxs-lookup"><span data-stu-id="bfac9-106">Updating Q# Projects</span></span> 

1. <span data-ttu-id="bfac9-107">Installera först den senaste versionen av [.NET Core SDK 3,0](https://dotnet.microsoft.com/download) och kör följande kommando i kommando tolken:</span><span class="sxs-lookup"><span data-stu-id="bfac9-107">First, install the latest version of the [.NET Core SDK 3.0](https://dotnet.microsoft.com/download) and run the following command in the command prompt:</span></span>
```bash
dotnet --version
```
 <span data-ttu-id="bfac9-108">Kontrol lera att utdata är 3.0.100 eller högre, och följ anvisningarna nedan beroende på dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="bfac9-108">Verify the output is 3.0.100 or higher, then follow the instructions below depending on your setup.</span></span>

### <a name="in-visual-studio"></a><span data-ttu-id="bfac9-109">I Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="bfac9-109">In Visual Studio</span></span>
 
 1. <span data-ttu-id="bfac9-110">Uppdatera till den senaste versionen av Visual Studio 2019 finns [här](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) för instruktioner</span><span class="sxs-lookup"><span data-stu-id="bfac9-110">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
 2. <span data-ttu-id="bfac9-111">Öppna din lösning i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bfac9-111">Open your solution in Visual Studio</span></span>
 3. <span data-ttu-id="bfac9-112">På menyn väljer du build > ren lösning</span><span class="sxs-lookup"><span data-stu-id="bfac9-112">From the menu, select Build > Clean Solution</span></span> 
 4. <span data-ttu-id="bfac9-113">[Uppdatera mål ramverket](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) i var och en av dina. CSPROJ-filer till netcoreapp 3.0 (eller netstandard 2.1 om det är ett biblioteks projekt)</span><span class="sxs-lookup"><span data-stu-id="bfac9-113">[Update the target framework](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
 5. <span data-ttu-id="bfac9-114">Spara och Stäng alla filer i lösningen</span><span class="sxs-lookup"><span data-stu-id="bfac9-114">Save and close all files in your solution</span></span>
 6. <span data-ttu-id="bfac9-115">Välj Verktyg > kommando rad > Developer kommando tolken</span><span class="sxs-lookup"><span data-stu-id="bfac9-115">Select Tools > Command Line > Developer Command Prompt</span></span>
 7. <span data-ttu-id="bfac9-116">Kör följande kommando för varje projekt i lösningen:</span><span class="sxs-lookup"><span data-stu-id="bfac9-116">For each project in the solution, run the following command:</span></span>
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
<span data-ttu-id="bfac9-117">Om dina projekt använder andra Microsoft. Quantum-paket kör du kommandot för dessa.</span><span class="sxs-lookup"><span data-stu-id="bfac9-117">If your projects use any other Microsoft.Quantum packages, run the command for these too.</span></span> 
 8. <span data-ttu-id="bfac9-118">Stäng kommando tolken och välj build > build-lösning (Välj *inte* att återskapa lösningen, eftersom återställningen kommer att Miss Förslut ATS)</span><span class="sxs-lookup"><span data-stu-id="bfac9-118">Close the command prompt and select Build > Build Solution (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

### <a name="in-visual-studio-code"></a><span data-ttu-id="bfac9-119">I Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="bfac9-119">In Visual Studio Code</span></span>

1. <span data-ttu-id="bfac9-120">Öppna mappen som innehåller projektet som ska uppdateras i Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="bfac9-120">In Visual Studio Code, open the folder containing the project to update</span></span>
1. <span data-ttu-id="bfac9-121">Välj Terminal > ny terminal</span><span class="sxs-lookup"><span data-stu-id="bfac9-121">Select Terminal > New Terminal</span></span>
1. <span data-ttu-id="bfac9-122">Följ anvisningarna för att uppdatera med hjälp av kommando raden</span><span class="sxs-lookup"><span data-stu-id="bfac9-122">Follow the instructions for updating using the command line</span></span>

### <a name="using-the-command-line"></a><span data-ttu-id="bfac9-123">Använda kommando raden</span><span class="sxs-lookup"><span data-stu-id="bfac9-123">Using the command line</span></span>

1. <span data-ttu-id="bfac9-124">Navigera till mappen som innehåller projekt filen</span><span class="sxs-lookup"><span data-stu-id="bfac9-124">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="bfac9-125">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bfac9-125">Run the following command:</span></span>
```bash
dotnet clean [project_name].csproj
```

3. <span data-ttu-id="bfac9-126">[Uppdatera mål ramverket](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) i var och en av dina. CSPROJ-filer till netcoreapp 3.0 (eller netstandard 2.1 om det är ett biblioteks projekt)</span><span class="sxs-lookup"><span data-stu-id="bfac9-126">[Update the target framework](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
4. <span data-ttu-id="bfac9-127">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="bfac9-127">Run the following command:</span></span>
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
<span data-ttu-id="bfac9-128">om projektet använder andra Microsoft. Quantum-paket kör du kommandot för dessa.</span><span class="sxs-lookup"><span data-stu-id="bfac9-128">if your project uses any other Microsoft.Quantum packages, run the command for these too.</span></span>

5. <span data-ttu-id="bfac9-129">Spara och Stäng alla filer</span><span class="sxs-lookup"><span data-stu-id="bfac9-129">Save and close all files</span></span>
6. <span data-ttu-id="bfac9-130">Upprepa 1-4 för varje projekt beroende och gå sedan tillbaka till mappen som innehåller huvud projektet och kör:</span><span class="sxs-lookup"><span data-stu-id="bfac9-130">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a><span data-ttu-id="bfac9-131">Uppdatera SWEETIQ # för python</span><span class="sxs-lookup"><span data-stu-id="bfac9-131">Update IQ# for Python</span></span>

1. <span data-ttu-id="bfac9-132">Uppdatera `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="bfac9-132">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="bfac9-133">Verifiera `iqsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="bfac9-133">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="bfac9-134">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="bfac9-134">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. <span data-ttu-id="bfac9-135">Uppdatera `qsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="bfac9-135">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="bfac9-136">Verifiera `qsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="bfac9-136">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="bfac9-137">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="bfac9-137">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. <span data-ttu-id="bfac9-138">Kör följande kommando från platsen för dina `.qs`-filer</span><span class="sxs-lookup"><span data-stu-id="bfac9-138">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. <span data-ttu-id="bfac9-139">Nu kan du använda den uppdaterade QDK-versionen för att köra befintliga Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="bfac9-139">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="bfac9-140">Uppdatera SWEETIQ # för Jupyter-anteckningsböcker</span><span class="sxs-lookup"><span data-stu-id="bfac9-140">Update IQ# for Jupyter notebooks</span></span>

1. <span data-ttu-id="bfac9-141">Uppdatera `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="bfac9-141">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="bfac9-142">Verifiera `iqsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="bfac9-142">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="bfac9-143">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="bfac9-143">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. <span data-ttu-id="bfac9-144">Kör följande kommando från en cell i Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="bfac9-144">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

1. <span data-ttu-id="bfac9-145">Nu kan du öppna en befintlig Jupyter-anteckningsbok och köra den med den uppdaterade QDK.</span><span class="sxs-lookup"><span data-stu-id="bfac9-145">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="bfac9-146">Uppdatera Visual Studio QDK-tillägg</span><span class="sxs-lookup"><span data-stu-id="bfac9-146">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="bfac9-147">Uppdatera Q # Visual Studio-tillägget</span><span class="sxs-lookup"><span data-stu-id="bfac9-147">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="bfac9-148">Visual Studio efterfrågar att du accepterar uppdateringar av [Quantum Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="bfac9-148">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="bfac9-149">Godkänn uppdateringen</span><span class="sxs-lookup"><span data-stu-id="bfac9-149">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="bfac9-150">Projektfilerna uppdateras med tillägget.</span><span class="sxs-lookup"><span data-stu-id="bfac9-150">The project templates are updated with the extension.</span></span> <span data-ttu-id="bfac9-151">De uppdaterade mallarna gäller endast för nyligen skapade projekt.</span><span class="sxs-lookup"><span data-stu-id="bfac9-151">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="bfac9-152">Koden för dina befintliga projekt uppdateras inte när tillägget uppdateras.</span><span class="sxs-lookup"><span data-stu-id="bfac9-152">The code for your existing projects is not updated when the extension is updated.</span></span>

## <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="bfac9-153">Uppdatera VS Code QDK-tillägg</span><span class="sxs-lookup"><span data-stu-id="bfac9-153">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="bfac9-154">Uppdatera tillägget för Quantum VS Code</span><span class="sxs-lookup"><span data-stu-id="bfac9-154">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="bfac9-155">Starta om VS-kod</span><span class="sxs-lookup"><span data-stu-id="bfac9-155">Restart VS Code</span></span>
    - <span data-ttu-id="bfac9-156">Navigera till fliken **tillägg**</span><span class="sxs-lookup"><span data-stu-id="bfac9-156">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="bfac9-157">Välj **Microsoft Quantum Development Kit för Visual Studio Code** -tillägg</span><span class="sxs-lookup"><span data-stu-id="bfac9-157">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="bfac9-158">Läs in tillägget igen</span><span class="sxs-lookup"><span data-stu-id="bfac9-158">Reload the extension</span></span>

1. <span data-ttu-id="bfac9-159">Uppdatera Quantum-projektmallar:</span><span class="sxs-lookup"><span data-stu-id="bfac9-159">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="bfac9-160">Gå till **Visa** -> **Kommandopaletten**</span><span class="sxs-lookup"><span data-stu-id="bfac9-160">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="bfac9-161">Välj **Q #: installera projektmallar**</span><span class="sxs-lookup"><span data-stu-id="bfac9-161">Select **Q#: Install project templates**</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="bfac9-162">C#, med hjälp av kommando rads verktyget `dotnet`</span><span class="sxs-lookup"><span data-stu-id="bfac9-162">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="bfac9-163">Uppdatera Quantum Project-mallar för .NET</span><span class="sxs-lookup"><span data-stu-id="bfac9-163">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="bfac9-164">Vad står på tur?</span><span class="sxs-lookup"><span data-stu-id="bfac9-164">What's next?</span></span>

<span data-ttu-id="bfac9-165">Nu när du har uppdaterat Quantum Development Kit i din önskade miljö kan du fortsätta att utveckla och köra dina Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="bfac9-165">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="bfac9-166">Om du inte har skrivit ett program ännu kan du komma igång med [ditt första Quantum-program](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="bfac9-166">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
