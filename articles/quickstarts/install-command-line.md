---
title: Utveckla med Q#-program i en IDE
description: Lär dig hur du skapar ett Q#-program som körs från kommandotolken.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: a6823888dcbe8cf79f0045d2615fe8b889dcc7c3
ms.sourcegitcommit: a13c7c86fd52a05cbf129b8dd713d6586ca1cc2c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93376430"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a><span data-ttu-id="123f3-103">Utveckla med Q#-program i en IDE</span><span class="sxs-lookup"><span data-stu-id="123f3-103">Develop with Q# applications in an IDE</span></span>

<span data-ttu-id="123f3-104">Q#-program kan köras fristående, utan någon drivrutin på ett värdspråk som C#, F# eller Python.</span><span class="sxs-lookup"><span data-stu-id="123f3-104">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span> <span data-ttu-id="123f3-105">Du kan utveckla Q#-program i Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces eller med valfritt redigeringsprogram/IDE-program och köra program från .NET-konsolen.</span><span class="sxs-lookup"><span data-stu-id="123f3-105">You can develop Q# applications in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, or with any editor/IDE and run applications from the .NET console.</span></span> 

## <a name="prerequisites-for-all-environments"></a><span data-ttu-id="123f3-106">Krav för alla miljöer</span><span class="sxs-lookup"><span data-stu-id="123f3-106">Prerequisites for all environments</span></span>

- [<span data-ttu-id="123f3-107">.NET Core SDK 3.1 eller senare</span><span class="sxs-lookup"><span data-stu-id="123f3-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="123f3-108">Installation</span><span class="sxs-lookup"><span data-stu-id="123f3-108">Installation</span></span>

<span data-ttu-id="123f3-109">Även om du kan skapa Q#-program i vilken IDE som helst, rekommenderar vi att du använder Visual Studio Code (VS Code) eller Visual Studio IDE när du utvecklar Q#-program lokalt.</span><span class="sxs-lookup"><span data-stu-id="123f3-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="123f3-110">Vi rekommenderar att du använder Visual Studio Codespaces om du tänker utveckla i molnet via en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="123f3-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="123f3-111">Utveckling i dessa miljöer använder de omfattande funktionerna i QDK-tillägget, däribland varningar, syntaxmarkeringar, projektmallar och mer.</span><span class="sxs-lookup"><span data-stu-id="123f3-111">Developing in these environments leverages the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

### <a name="to-configure-for-vs-code"></a><span data-ttu-id="123f3-112">Konfigurera för VS Code:</span><span class="sxs-lookup"><span data-stu-id="123f3-112">To configure for VS Code:</span></span>

1. <span data-ttu-id="123f3-113">Ladda ned och installera [VS Code](https://code.visualstudio.com/download) (Windows, Linux och Mac).</span><span class="sxs-lookup"><span data-stu-id="123f3-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="123f3-114">Installera [Microsoft QDK för VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="123f3-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

### <a name="to-configure-for-visual-studio"></a><span data-ttu-id="123f3-115">Konfigurera för Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="123f3-115">To configure for Visual Studio:</span></span>

1. <span data-ttu-id="123f3-116">Ladda ned och installera [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 eller senare, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat.</span><span class="sxs-lookup"><span data-stu-id="123f3-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="123f3-117">Ladda ned och installera [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="123f3-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

### <a name="to-configure-for-another-environment"></a><span data-ttu-id="123f3-118">Så här konfigurerar du för en annan miljö:</span><span class="sxs-lookup"><span data-stu-id="123f3-118">To configure for another environment:</span></span> 

1. <span data-ttu-id="123f3-119">Ange följande i kommandotolken</span><span class="sxs-lookup"><span data-stu-id="123f3-119">Enter the following at the command prompt</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a><span data-ttu-id="123f3-120">Så här konfigurerar du för Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="123f3-120">To configure for Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="123f3-121">Skapa ett [Azure-konto](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="123f3-121">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="123f3-122">Skapa en Codespaces-miljö.</span><span class="sxs-lookup"><span data-stu-id="123f3-122">Create a Codespaces environment.</span></span> <span data-ttu-id="123f3-123">Följ [snabbstartsguiden](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="123f3-123">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="123f3-124">När du skapar ett codespace rekommenderar vi att du anger `microsoft/Quantum` i fältet Git Repository (Git-lagringsplats) för att läsa in QDK-specifika inställningar.</span><span class="sxs-lookup"><span data-stu-id="123f3-124">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="123f3-125">Nu kan du starta din nya miljö och börja utveckla i webbläsaren via [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="123f3-125">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="123f3-126">Du kan också använda en lokal installation av VS Code och använda Codespaces som en [fjärrmiljö](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="123f3-126">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>

## <a name="develop-with-no-locq"></a><span data-ttu-id="123f3-127">Utveckla med Q#</span><span class="sxs-lookup"><span data-stu-id="123f3-127">Develop with Q#</span></span>

<span data-ttu-id="123f3-128">Följ anvisningarna i den flik som motsvarar din utvecklingsmiljö.</span><span class="sxs-lookup"><span data-stu-id="123f3-128">Follow the instructions on the tab corresponding to your development environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="123f3-129">VS-kod</span><span class="sxs-lookup"><span data-stu-id="123f3-129">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="123f3-130">Skapa ett nytt projekt:</span><span class="sxs-lookup"><span data-stu-id="123f3-130">To create a new project:</span></span>

1. <span data-ttu-id="123f3-131">Klicka på **Visa** -> **Kommandopalett** och välj **Q#: Skapa nytt projekt**.</span><span class="sxs-lookup"><span data-stu-id="123f3-131">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="123f3-132">Klicka på **Fristående konsolprogram**.</span><span class="sxs-lookup"><span data-stu-id="123f3-132">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="123f3-133">Gå till platsen där du vill spara projektet och klicka på **Skapa projekt**.</span><span class="sxs-lookup"><span data-stu-id="123f3-133">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="123f3-134">När projektet har skapats klickar du på **Öppna nytt projekt...** längst ned till höger.</span><span class="sxs-lookup"><span data-stu-id="123f3-134">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="123f3-135">Inspektera projektet.</span><span class="sxs-lookup"><span data-stu-id="123f3-135">Inspect the project.</span></span> <span data-ttu-id="123f3-136">Du bör se en källfil med namnet `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="123f3-136">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="123f3-137">Så här kör du programmet:</span><span class="sxs-lookup"><span data-stu-id="123f3-137">To run the application:</span></span>

1. <span data-ttu-id="123f3-138">Välj **Terminal** -> **Ny terminal**.</span><span class="sxs-lookup"><span data-stu-id="123f3-138">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="123f3-139">I terminalprompten anger du `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="123f3-139">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="123f3-140">Du bör se följande text i utdatafönstret `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="123f3-140">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="123f3-141">Arbetsytor med flera rotmappar stöds för närvarande inte av VS Code-tillägget för Q#.</span><span class="sxs-lookup"><span data-stu-id="123f3-141">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="123f3-142">Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.</span><span class="sxs-lookup"><span data-stu-id="123f3-142">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="123f3-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="123f3-143">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="123f3-144">Verifiera din Visual Studio-installation genom att skapa ett Q#-program för `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="123f3-144">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="123f3-145">Så här skapar du ett nytt Q#-program:</span><span class="sxs-lookup"><span data-stu-id="123f3-145">To create a new Q# application:</span></span>

1. <span data-ttu-id="123f3-146">Öppna Visual Studio och klicka på **Arkiv** -> **Nytt** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="123f3-146">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="123f3-147">Skriv `Q#` i sökrutan, välj **Q#-program** och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="123f3-147">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="123f3-148">Ange ett namn och en plats för programmet och klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="123f3-148">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="123f3-149">Inspektera projektet.</span><span class="sxs-lookup"><span data-stu-id="123f3-149">Inspect the project.</span></span> <span data-ttu-id="123f3-150">Du bör se en källfil med namnet `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="123f3-150">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="123f3-151">Så här kör du programmet:</span><span class="sxs-lookup"><span data-stu-id="123f3-151">To run the application:</span></span>

1. <span data-ttu-id="123f3-152">Välj **Felsökning** -> **Starta utan felsökning**.</span><span class="sxs-lookup"><span data-stu-id="123f3-152">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="123f3-153">Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.</span><span class="sxs-lookup"><span data-stu-id="123f3-153">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="123f3-154">Om du har flera projekt i en Visual Studio-lösning, måste alla projekt i lösningen finnas i samma mapp som lösningen eller i någon av dess undermappar.</span><span class="sxs-lookup"><span data-stu-id="123f3-154">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="123f3-155">Andra redigeringsprogram med kommandotolken</span><span class="sxs-lookup"><span data-stu-id="123f3-155">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="123f3-156">Verifiera din installation genom att skapa ett Q# `Hello World`-program.</span><span class="sxs-lookup"><span data-stu-id="123f3-156">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="123f3-157">Skapa ett nytt program:</span><span class="sxs-lookup"><span data-stu-id="123f3-157">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="123f3-158">Gå till programkatalogen:</span><span class="sxs-lookup"><span data-stu-id="123f3-158">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="123f3-159">Den här katalogen bör du innehålla filen `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="123f3-159">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="123f3-160">Du kan ändra den här mallen med ett textredigeringsprogram och skriva över den med dina egna kvantprogram.</span><span class="sxs-lookup"><span data-stu-id="123f3-160">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="123f3-161">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="123f3-161">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="123f3-162">Du bör se följande text skrivas ut: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="123f3-162">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="123f3-163">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="123f3-163">Next steps</span></span>

<span data-ttu-id="123f3-164">Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="123f3-164">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
