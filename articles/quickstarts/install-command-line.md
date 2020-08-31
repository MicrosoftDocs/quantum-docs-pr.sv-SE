---
title: Utveckla med Q#-program
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6a287dd76162a05d72af7e9d1e46533425283e2a
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863668"
---
# <a name="develop-with-no-locq-applications"></a><span data-ttu-id="f49bf-102">Utveckla med Q#-program</span><span class="sxs-lookup"><span data-stu-id="f49bf-102">Develop with Q# applications</span></span>

<span data-ttu-id="f49bf-103">Q#-program kan köras fristående, utan någon drivrutin på ett värdspråk som C#, F# eller Python.</span><span class="sxs-lookup"><span data-stu-id="f49bf-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f49bf-104">Krav</span><span class="sxs-lookup"><span data-stu-id="f49bf-104">Prerequisites</span></span>

- [<span data-ttu-id="f49bf-105">.NET Core SDK 3.1 eller senare</span><span class="sxs-lookup"><span data-stu-id="f49bf-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="f49bf-106">Installation</span><span class="sxs-lookup"><span data-stu-id="f49bf-106">Installation</span></span>

<span data-ttu-id="f49bf-107">Även om du kan skapa Q#-program i vilken IDE som helst, rekommenderar vi att du använder Visual Studio Code (VS Code) eller Visual Studio IDE när du utvecklar Q#-program lokalt.</span><span class="sxs-lookup"><span data-stu-id="f49bf-107">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="f49bf-108">Vi rekommenderar att du använder Visual Studio Codespaces om du tänker utveckla i molnet via en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="f49bf-108">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="f49bf-109">Utveckling i dessa miljöer inbegriper de omfattande funktionerna i QDK-tillägget, däribland varningar, syntaxmarkeringar, projektmallar och mer.</span><span class="sxs-lookup"><span data-stu-id="f49bf-109">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="f49bf-110">Konfigurera VS Code:</span><span class="sxs-lookup"><span data-stu-id="f49bf-110">To configure VS Code:</span></span>

1. <span data-ttu-id="f49bf-111">Ladda ned och installera [VS Code](https://code.visualstudio.com/download) (Windows, Linux och Mac).</span><span class="sxs-lookup"><span data-stu-id="f49bf-111">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="f49bf-112">Installera [Microsoft QDK för VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="f49bf-112">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="f49bf-113">Konfigurera Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="f49bf-113">To configure Visual Studio:</span></span>

1. <span data-ttu-id="f49bf-114">Ladda ned och installera [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 eller senare, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat.</span><span class="sxs-lookup"><span data-stu-id="f49bf-114">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="f49bf-115">Ladda ned och installera [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="f49bf-115">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="f49bf-116">Så här konfigurerar du Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="f49bf-116">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="f49bf-117">Skapa ett [Azure-konto](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="f49bf-117">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="f49bf-118">Skapa en Codespaces-miljö.</span><span class="sxs-lookup"><span data-stu-id="f49bf-118">Create a Codespaces environment.</span></span> <span data-ttu-id="f49bf-119">Följ [snabbstartsguiden](https://docs.microsoft.com/visualstudio/online/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="f49bf-119">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/online/quickstarts/browser).</span></span> <span data-ttu-id="f49bf-120">När du skapar ett codespace rekommenderar vi att du anger `microsoft/Quantum` i fältet Git Repository (Git-lagringsplats) för att läsa in QDK-specifika inställningar.</span><span class="sxs-lookup"><span data-stu-id="f49bf-120">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="f49bf-121">Nu kan du starta din nya miljö och börja utveckla i webbläsaren via [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="f49bf-121">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="f49bf-122">Du kan också använda en lokal installation av VS Code och använda Codespaces som en [fjärrmiljö](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="f49bf-122">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="f49bf-123">Installera QDK för en annan miljö genom att ange följande i kommandotolken:</span><span class="sxs-lookup"><span data-stu-id="f49bf-123">To install the QDK for another environment, enter at the command prompt:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="f49bf-124">Utveckla med Q#</span><span class="sxs-lookup"><span data-stu-id="f49bf-124">Develop with Q#</span></span>

<span data-ttu-id="f49bf-125">Följ anvisningarna på den flik som motsvarar din miljö.</span><span class="sxs-lookup"><span data-stu-id="f49bf-125">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="f49bf-126">VS-kod</span><span class="sxs-lookup"><span data-stu-id="f49bf-126">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f49bf-127">Skapa ett nytt projekt:</span><span class="sxs-lookup"><span data-stu-id="f49bf-127">To create a new project:</span></span>

1. <span data-ttu-id="f49bf-128">Klicka på **Visa** -> **Kommandopalett** och välj **Q#: Skapa nytt projekt**.</span><span class="sxs-lookup"><span data-stu-id="f49bf-128">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="f49bf-129">Klicka på **Fristående konsolprogram**.</span><span class="sxs-lookup"><span data-stu-id="f49bf-129">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="f49bf-130">Gå till platsen där du vill spara projektet och klicka på **Skapa projekt**.</span><span class="sxs-lookup"><span data-stu-id="f49bf-130">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="f49bf-131">När projektet har skapats klickar du på **Öppna nytt projekt...** längst ned till höger.</span><span class="sxs-lookup"><span data-stu-id="f49bf-131">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="f49bf-132">Inspektera projektet.</span><span class="sxs-lookup"><span data-stu-id="f49bf-132">Inspect the project.</span></span> <span data-ttu-id="f49bf-133">Du bör se en källfil med namnet `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="f49bf-133">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="f49bf-134">Så här kör du programmet:</span><span class="sxs-lookup"><span data-stu-id="f49bf-134">To run the application:</span></span>
1. <span data-ttu-id="f49bf-135">Välj **Terminal** -> **Ny terminal**.</span><span class="sxs-lookup"><span data-stu-id="f49bf-135">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="f49bf-136">I terminalprompten anger du `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="f49bf-136">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="f49bf-137">Du bör se följande text i utdatafönstret `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="f49bf-137">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="f49bf-138">Arbetsytor med flera rotmappar stöds för närvarande inte av VS Code-tillägget för Q#.</span><span class="sxs-lookup"><span data-stu-id="f49bf-138">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="f49bf-139">Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.</span><span class="sxs-lookup"><span data-stu-id="f49bf-139">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="f49bf-140">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f49bf-140">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="f49bf-141">Verifiera din Visual Studio-installation genom att skapa ett Q#-program för `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="f49bf-141">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="f49bf-142">Så här skapar du ett nytt Q#-program:</span><span class="sxs-lookup"><span data-stu-id="f49bf-142">To create a new Q# application:</span></span>
1. <span data-ttu-id="f49bf-143">Öppna Visual Studio och klicka på **Arkiv** -> **Nytt** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="f49bf-143">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="f49bf-144">Skriv `Q#` i sökrutan, välj **Q#-program** och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f49bf-144">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="f49bf-145">Ange ett namn och en plats för programmet och klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="f49bf-145">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="f49bf-146">Inspektera projektet.</span><span class="sxs-lookup"><span data-stu-id="f49bf-146">Inspect the project.</span></span> <span data-ttu-id="f49bf-147">Du bör se en källfil med namnet `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="f49bf-147">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="f49bf-148">Så här kör du programmet:</span><span class="sxs-lookup"><span data-stu-id="f49bf-148">To run the application:</span></span>
1. <span data-ttu-id="f49bf-149">Välj **Felsökning** -> **Starta utan felsökning**.</span><span class="sxs-lookup"><span data-stu-id="f49bf-149">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="f49bf-150">Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.</span><span class="sxs-lookup"><span data-stu-id="f49bf-150">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="f49bf-151">Om du har flera projekt i en Visual Studio-lösning, måste alla projekt i lösningen finnas i samma mapp som lösningen eller i någon av dess undermappar.</span><span class="sxs-lookup"><span data-stu-id="f49bf-151">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="f49bf-152">Andra redigeringsprogram med kommandotolken</span><span class="sxs-lookup"><span data-stu-id="f49bf-152">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="f49bf-153">Verifiera din installation genom att skapa ett Q# `Hello World`-program.</span><span class="sxs-lookup"><span data-stu-id="f49bf-153">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="f49bf-154">Installera projektmallarna.</span><span class="sxs-lookup"><span data-stu-id="f49bf-154">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="f49bf-155">Skapa ett nytt program:</span><span class="sxs-lookup"><span data-stu-id="f49bf-155">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="f49bf-156">Gå till programkatalogen:</span><span class="sxs-lookup"><span data-stu-id="f49bf-156">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="f49bf-157">Den här katalogen bör du innehålla filen `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="f49bf-157">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="f49bf-158">Du kan ändra den här mallen med ett textredigeringsprogram och skriva över den med dina egna kvantprogram.</span><span class="sxs-lookup"><span data-stu-id="f49bf-158">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="f49bf-159">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="f49bf-159">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="f49bf-160">Du bör se följande text skrivas ut: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="f49bf-160">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="f49bf-161">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f49bf-161">Next steps</span></span>

<span data-ttu-id="f49bf-162">Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="f49bf-162">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
