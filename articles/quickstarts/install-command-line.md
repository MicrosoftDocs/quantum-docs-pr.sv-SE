---
title: Utveckla med Q#-kommandoradsprogram
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884274"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="5b1fe-102">Utveckla med Q#-kommandoradsprogram</span><span class="sxs-lookup"><span data-stu-id="5b1fe-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="5b1fe-103">Q#-program kan köras fristående, utan någon drivrutin på ett värdspråk som C#, F# eller Python.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5b1fe-104">Krav</span><span class="sxs-lookup"><span data-stu-id="5b1fe-104">Prerequisites</span></span>

- [<span data-ttu-id="5b1fe-105">.NET Core SDK 3.1 eller senare</span><span class="sxs-lookup"><span data-stu-id="5b1fe-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="5b1fe-106">Installation</span><span class="sxs-lookup"><span data-stu-id="5b1fe-106">Installation</span></span>

<span data-ttu-id="5b1fe-107">Även om du kan skapa Q#-kommandoradsprogram i vilken IDE som helst, rekommenderar vi att du använder IDE:n för Visual Studio Code (VS Code) eller Visual Studio till dina Q#-program.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="5b1fe-108">Utveckling i dessa miljöer inbegriper de omfattande funktionerna i QDK-tillägget, däribland varningar, syntaxmarkeringar, projektmallar och mer.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-108">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="5b1fe-109">Konfigurera VS Code:</span><span class="sxs-lookup"><span data-stu-id="5b1fe-109">To configure VS Code:</span></span>

1. <span data-ttu-id="5b1fe-110">Ladda ned och installera [VS Code](https://code.visualstudio.com/download) (Windows, Linux och Mac).</span><span class="sxs-lookup"><span data-stu-id="5b1fe-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="5b1fe-111">Installera [Microsoft QDK för VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="5b1fe-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="5b1fe-112">Konfigurera Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="5b1fe-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="5b1fe-113">Ladda ned och installera [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 eller senare, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="5b1fe-114">Ladda ned och installera [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="5b1fe-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="5b1fe-115">Installera QDK för en annan miljö genom att ange följande på kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="5b1fe-115">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="5b1fe-116">Utveckla med Q#</span><span class="sxs-lookup"><span data-stu-id="5b1fe-116">Develop with Q#</span></span>

<span data-ttu-id="5b1fe-117">Följ anvisningarna på den flik som motsvarar din miljö.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-117">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="5b1fe-118">VS-kod</span><span class="sxs-lookup"><span data-stu-id="5b1fe-118">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="5b1fe-119">Installera Q#-projektmallarna:</span><span class="sxs-lookup"><span data-stu-id="5b1fe-119">Install the Q# project templates:</span></span>

1. <span data-ttu-id="5b1fe-120">Öppna VS Code.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-120">Open VS Code.</span></span>
2. <span data-ttu-id="5b1fe-121">Klicka på **Visa** -> **Kommandopalett**.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-121">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="5b1fe-122">Välj **Q#: Installera projektmallar**.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-122">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="5b1fe-123">När **Projektmallar har installerats** visas, kan QDK:n användas med dina egna program och bibliotek.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-123">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="5b1fe-124">Skapa ett nytt projekt:</span><span class="sxs-lookup"><span data-stu-id="5b1fe-124">To create a new project:</span></span>

1. <span data-ttu-id="5b1fe-125">Klicka på **Visa** -> **Kommandopalett** och välj **Q#: Skapa nytt projekt**.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-125">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="5b1fe-126">Klicka på **Fristående konsolprogram**.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-126">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="5b1fe-127">Gå till platsen där du vill spara projektet och klicka på **Skapa projekt**.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-127">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="5b1fe-128">När projektet har skapats klickar du på **Öppna nytt projekt...** längst ned till höger.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-128">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="5b1fe-129">Inspektera projektet.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-129">Inspect the project.</span></span> <span data-ttu-id="5b1fe-130">Du bör se en källfil med namnet `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-130">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="5b1fe-131">Så här kör du programmet:</span><span class="sxs-lookup"><span data-stu-id="5b1fe-131">To run the application:</span></span>
1. <span data-ttu-id="5b1fe-132">Välj **Terminal** -> **Ny terminal**.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-132">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="5b1fe-133">I terminalprompten anger du `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-133">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="5b1fe-134">Du bör se följande text i utdatafönstret `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="5b1fe-134">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="5b1fe-135">Arbetsytor med flera rotmappar stöds för närvarande inte av VS Code-tillägget för Q#.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-135">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="5b1fe-136">Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-136">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="5b1fe-137">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b1fe-137">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="5b1fe-138">Verifiera din Visual Studio-installation genom att skapa ett Q# `Hello World`-program.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-138">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="5b1fe-139">Skapa ett nytt Q#-program:</span><span class="sxs-lookup"><span data-stu-id="5b1fe-139">To create a new Q# application:</span></span>
1. <span data-ttu-id="5b1fe-140">Öppna Visual Studio och klicka på **Arkiv** -> **Nytt** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-140">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="5b1fe-141">Skriv `Q#` i sökrutan, välj **Q#-program** och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-141">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="5b1fe-142">Ange ett namn och en plats för programmet och klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-142">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="5b1fe-143">Inspektera projektet.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-143">Inspect the project.</span></span> <span data-ttu-id="5b1fe-144">Du bör se en källfil med namnet `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-144">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="5b1fe-145">Så här kör du programmet:</span><span class="sxs-lookup"><span data-stu-id="5b1fe-145">To run the application:</span></span>
1. <span data-ttu-id="5b1fe-146">Välj **Felsökning** -> **Starta utan felsökning**.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-146">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="5b1fe-147">Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-147">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="5b1fe-148">Om du har flera projekt i en Visual Studio-lösning, måste alla projekt i lösningen finnas i samma mapp som lösningen eller i någon av dess undermappar.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-148">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="5b1fe-149">Andra redigeringsprogram med kommandoraden</span><span class="sxs-lookup"><span data-stu-id="5b1fe-149">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="5b1fe-150">Verifiera din installation genom att skapa ett Q# `Hello World`-program.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-150">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="5b1fe-151">Skapa ett nytt program:</span><span class="sxs-lookup"><span data-stu-id="5b1fe-151">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. <span data-ttu-id="5b1fe-152">Gå till programkatalogen:</span><span class="sxs-lookup"><span data-stu-id="5b1fe-152">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="5b1fe-153">Den här katalogen bör du innehålla filen `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-153">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="5b1fe-154">Du kan ändra den här mallen med ett textredigeringsprogram och skriva över den med dina egna kvantprogram.</span><span class="sxs-lookup"><span data-stu-id="5b1fe-154">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

3. <span data-ttu-id="5b1fe-155">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="5b1fe-155">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

4. <span data-ttu-id="5b1fe-156">Du bör se följande text skrivas ut: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="5b1fe-156">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="5b1fe-157">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5b1fe-157">Next steps</span></span>

<span data-ttu-id="5b1fe-158">Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="5b1fe-158">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
