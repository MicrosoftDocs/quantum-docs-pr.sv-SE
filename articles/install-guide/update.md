---
title: Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185859"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="f0c23-102">Uppdatera Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="f0c23-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="f0c23-103">Lär dig hur du uppdaterar Microsoft Quantum Development Kit (QDK) till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="f0c23-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="f0c23-104">Den här artikeln förutsätter att du redan har installerat QDK.</span><span class="sxs-lookup"><span data-stu-id="f0c23-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="f0c23-105">Om du installerar för första gången kan du läsa [installations guiden](xref:microsoft.quantum.install)för.</span><span class="sxs-lookup"><span data-stu-id="f0c23-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="f0c23-106">Uppdaterings stegen är beroende av utvecklings miljön.</span><span class="sxs-lookup"><span data-stu-id="f0c23-106">The update steps depend on your development environment.</span></span> <span data-ttu-id="f0c23-107">Välj din miljö i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="f0c23-107">Choose your environment from the following sections.</span></span>

## <a name="python"></a><span data-ttu-id="f0c23-108">Python</span><span class="sxs-lookup"><span data-stu-id="f0c23-108">Python</span></span>

1. <span data-ttu-id="f0c23-109">Uppdatera `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="f0c23-109">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="f0c23-110">Verifiera `iqsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="f0c23-110">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="f0c23-111">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="f0c23-111">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="f0c23-112">Uppdatera `qsharp`-paketet</span><span class="sxs-lookup"><span data-stu-id="f0c23-112">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="f0c23-113">Verifiera `qsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="f0c23-113">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="f0c23-114">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="f0c23-114">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="f0c23-115">Nu kan du använda den uppdaterade QDK-versionen för att köra befintliga Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="f0c23-115">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="jupyter-notebooks"></a><span data-ttu-id="f0c23-116">Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="f0c23-116">Jupyter notebooks</span></span>

1. <span data-ttu-id="f0c23-117">Uppdatera `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="f0c23-117">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="f0c23-118">Verifiera `iqsharp` versionen</span><span class="sxs-lookup"><span data-stu-id="f0c23-118">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="f0c23-119">Du bör se följande utdata:</span><span class="sxs-lookup"><span data-stu-id="f0c23-119">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="f0c23-120">Nu kan du öppna en befintlig Jupyter-anteckningsbok och köra den med den uppdaterade QDK.</span><span class="sxs-lookup"><span data-stu-id="f0c23-120">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="c-on-windows-using-visual-studio"></a><span data-ttu-id="f0c23-121">C#i Windows använder du Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f0c23-121">C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="f0c23-122">Uppdatera Q # Visual Studio-tillägget</span><span class="sxs-lookup"><span data-stu-id="f0c23-122">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="f0c23-123">Visual Studio efterfrågar att du accepterar uppdateringar av [Quantum Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="f0c23-123">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="f0c23-124">Godkänn uppdateringen</span><span class="sxs-lookup"><span data-stu-id="f0c23-124">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="f0c23-125">Projektfilerna uppdateras med tillägget.</span><span class="sxs-lookup"><span data-stu-id="f0c23-125">The project templates are updated with the extension.</span></span> <span data-ttu-id="f0c23-126">De uppdaterade mallarna gäller endast för nyligen skapade projekt.</span><span class="sxs-lookup"><span data-stu-id="f0c23-126">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="f0c23-127">Koden för dina befintliga projekt uppdateras inte när tillägget uppdateras.</span><span class="sxs-lookup"><span data-stu-id="f0c23-127">The code for your existing projects is not updated when the extension is updated.</span></span>

1. <span data-ttu-id="f0c23-128">Uppdatera QDK-paketen</span><span class="sxs-lookup"><span data-stu-id="f0c23-128">Update the QDK packages</span></span>

    - <span data-ttu-id="f0c23-129">Öppna ett befintligt program</span><span class="sxs-lookup"><span data-stu-id="f0c23-129">Open an existing application</span></span>
    - <span data-ttu-id="f0c23-130">Välj **beroenden** i Solution Explorer</span><span class="sxs-lookup"><span data-stu-id="f0c23-130">Select **Dependencies** in the Solution Explorer</span></span>
    - <span data-ttu-id="f0c23-131">Välj **Hantera NuGet-paket**</span><span class="sxs-lookup"><span data-stu-id="f0c23-131">Select **Manage NuGet Packages**</span></span>
    - <span data-ttu-id="f0c23-132">Uppdatera **Microsoft. Quantum** -paketen till den senaste versionen</span><span class="sxs-lookup"><span data-stu-id="f0c23-132">Update the **Microsoft.Quantum** packages to the latest version</span></span>

1. <span data-ttu-id="f0c23-133">Nu kan du köra ditt program med de senaste QDK.</span><span class="sxs-lookup"><span data-stu-id="f0c23-133">You can now run your application with the latest QDK.</span></span>

## <a name="c-using-vs-code"></a><span data-ttu-id="f0c23-134">C#, med VS Code</span><span class="sxs-lookup"><span data-stu-id="f0c23-134">C#, using VS Code</span></span>

1. <span data-ttu-id="f0c23-135">Uppdatera tillägget för Quantum VS Code</span><span class="sxs-lookup"><span data-stu-id="f0c23-135">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="f0c23-136">Starta om VS-kod</span><span class="sxs-lookup"><span data-stu-id="f0c23-136">Restart VS Code</span></span>
    - <span data-ttu-id="f0c23-137">Navigera till fliken **tillägg**</span><span class="sxs-lookup"><span data-stu-id="f0c23-137">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="f0c23-138">Välj **Microsoft Quantum Development Kit för Visual Studio Code** -tillägg</span><span class="sxs-lookup"><span data-stu-id="f0c23-138">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="f0c23-139">Läs in tillägget igen</span><span class="sxs-lookup"><span data-stu-id="f0c23-139">Reload the extension</span></span>

1. <span data-ttu-id="f0c23-140">Uppdatera Quantum-projektmallar:</span><span class="sxs-lookup"><span data-stu-id="f0c23-140">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="f0c23-141">Gå till **visa** -> **kommando paletten**</span><span class="sxs-lookup"><span data-stu-id="f0c23-141">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="f0c23-142">Välj **Q #: installera projektmallar**</span><span class="sxs-lookup"><span data-stu-id="f0c23-142">Select **Q#: Install project templates**</span></span>

1. <span data-ttu-id="f0c23-143">Öppna ett befintligt program i VS Code</span><span class="sxs-lookup"><span data-stu-id="f0c23-143">Open an existing application in VS Code</span></span>

   - <span data-ttu-id="f0c23-144">Redigera. CSPROJ-filen för att lägga till nya paket versioner</span><span class="sxs-lookup"><span data-stu-id="f0c23-144">Edit the .csproj file to add the new package versions</span></span>

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    <span data-ttu-id="f0c23-145">Om du använder andra `Microsoft.Quantum`-paket uppdaterar du dem också.</span><span class="sxs-lookup"><span data-stu-id="f0c23-145">If you use other `Microsoft.Quantum` packages, update these too.</span></span>

1. <span data-ttu-id="f0c23-146">Nu kan du köra ditt program med den uppdaterade QDK</span><span class="sxs-lookup"><span data-stu-id="f0c23-146">You can now run your application with the updated QDK</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="f0c23-147">C#, med hjälp av kommando rads verktyget `dotnet`</span><span class="sxs-lookup"><span data-stu-id="f0c23-147">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="f0c23-148">Uppdatera Quantum Project-mallar för .NET</span><span class="sxs-lookup"><span data-stu-id="f0c23-148">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="f0c23-149">Uppdatera och köra ett befintligt program</span><span class="sxs-lookup"><span data-stu-id="f0c23-149">Update and run an existing application</span></span>

    - <span data-ttu-id="f0c23-150">Uppdatera QDK-paket versionerna i ditt program</span><span class="sxs-lookup"><span data-stu-id="f0c23-150">Update the QDK package versions in your application</span></span>

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        <span data-ttu-id="f0c23-151">Om programmet använder andra `Microsoft.Quantum`-paket uppdaterar du dem också.</span><span class="sxs-lookup"><span data-stu-id="f0c23-151">If your application uses any other `Microsoft.Quantum` packages, update these too.</span></span>

    - <span data-ttu-id="f0c23-152">Köra programmet</span><span class="sxs-lookup"><span data-stu-id="f0c23-152">Run the application</span></span>

        ```bash
        dotnet run
        ```

    - <span data-ttu-id="f0c23-153">Programmet kommer att köras med de nya paket versionerna</span><span class="sxs-lookup"><span data-stu-id="f0c23-153">Your application will run with the new package versions</span></span>

## <a name="whats-next"></a><span data-ttu-id="f0c23-154">Vad står på tur?</span><span class="sxs-lookup"><span data-stu-id="f0c23-154">What's next?</span></span>

<span data-ttu-id="f0c23-155">Nu när du har uppdaterat Quantum Development Kit i din önskade miljö kan du fortsätta att utveckla och köra dina Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="f0c23-155">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="f0c23-156">Om du inte har skrivit ett program ännu kan du komma igång med [ditt första Quantum-program](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="f0c23-156">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
