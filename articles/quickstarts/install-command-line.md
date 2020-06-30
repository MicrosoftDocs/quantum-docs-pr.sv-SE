---
title: Utveckla med Q#-kommandoradsprogram
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274194"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="2ff2c-102">Utveckla med Q#-kommandoradsprogram</span><span class="sxs-lookup"><span data-stu-id="2ff2c-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="2ff2c-103">Q#-program kan köras fristående, utan någon drivrutin på ett värdspråk som C#, F# eller Python.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2ff2c-104">Krav</span><span class="sxs-lookup"><span data-stu-id="2ff2c-104">Prerequisites</span></span>

- [<span data-ttu-id="2ff2c-105">.NET Core SDK 3.1 eller senare</span><span class="sxs-lookup"><span data-stu-id="2ff2c-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="2ff2c-106">Installation</span><span class="sxs-lookup"><span data-stu-id="2ff2c-106">Installation</span></span>

<span data-ttu-id="2ff2c-107">Även om du kan skapa Q#-kommandoradsprogram i vilken IDE som helst, rekommenderar vi att du använder IDE:n för Visual Studio Code (VS Code) eller Visual Studio till dina Q#-program.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="2ff2c-108">Utveckling med dessa verktyg ger tillgång till omfattande funktioner.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="2ff2c-109">Konfigurera VS Code:</span><span class="sxs-lookup"><span data-stu-id="2ff2c-109">To configure VS Code:</span></span>

1. <span data-ttu-id="2ff2c-110">Ladda ned och installera [VS Code](https://code.visualstudio.com/download) (Windows, Linux och Mac).</span><span class="sxs-lookup"><span data-stu-id="2ff2c-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="2ff2c-111">Installera [Microsoft QDK för VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="2ff2c-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="2ff2c-112">Konfigurera Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="2ff2c-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="2ff2c-113">Ladda ned och installera [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 eller senare, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="2ff2c-114">Ladda ned och installera [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="2ff2c-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="2ff2c-115">Utveckla i C# med VS Code</span><span class="sxs-lookup"><span data-stu-id="2ff2c-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="2ff2c-116">Installera Q#-projektmallarna:</span><span class="sxs-lookup"><span data-stu-id="2ff2c-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="2ff2c-117">Öppna VS Code.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-117">Open VS Code.</span></span>
2. <span data-ttu-id="2ff2c-118">Klicka på **Visa** -> **Kommandopalett**.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="2ff2c-119">Välj **Q#: Installera projektmallar**.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="2ff2c-120">När **Projektmallar har installerats** visas, kan QDK:n användas med dina egna program och bibliotek.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="2ff2c-121">Skapa ett nytt projekt:</span><span class="sxs-lookup"><span data-stu-id="2ff2c-121">To create a new project:</span></span>

1. <span data-ttu-id="2ff2c-122">Klicka på **Visa** -> **Kommandopalett** och välj **Q#: Skapa nytt projekt**.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="2ff2c-123">Klicka på **Fristående konsolprogram**.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="2ff2c-124">Gå till platsen där du vill spara projektet och klicka på **Skapa projekt**.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="2ff2c-125">När projektet har skapats klickar du på **Öppna nytt projekt...** längst ned till höger.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="2ff2c-126">Inspektera projektet.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-126">Inspect the project.</span></span> <span data-ttu-id="2ff2c-127">Du bör se en källfil med namnet `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="2ff2c-128">Så här kör du programmet:</span><span class="sxs-lookup"><span data-stu-id="2ff2c-128">To run the application:</span></span>
1. <span data-ttu-id="2ff2c-129">Välj **Terminal** -> **Ny terminal**.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="2ff2c-130">I terminalprompten anger du `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="2ff2c-131">Du bör se följande text i utdatafönstret `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="2ff2c-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="2ff2c-132">Arbetsytor med flera rotmappar stöds för närvarande inte av VS Code-tillägget för Q#.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="2ff2c-133">Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="2ff2c-134">Utveckla med Q# och Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2ff2c-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="2ff2c-135">Verifiera din Visual Studio-installation genom att skapa ett Q# `Hello World`-program.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="2ff2c-136">Skapa ett nytt Q#-program:</span><span class="sxs-lookup"><span data-stu-id="2ff2c-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="2ff2c-137">Öppna Visual Studio och klicka på **Arkiv** -> **Nytt** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="2ff2c-138">Skriv `Q#` i sökrutan, välj **Q#-program** och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="2ff2c-139">Ange ett namn och en plats för programmet och klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="2ff2c-140">Inspektera projektet.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-140">Inspect the project.</span></span> <span data-ttu-id="2ff2c-141">Du bör se en källfil med namnet `Program.qs`, vilket är ett Q#-program som definierar en enkel åtgärd för att skriva ut ett meddelande till konsolen.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="2ff2c-142">Så här kör du programmet:</span><span class="sxs-lookup"><span data-stu-id="2ff2c-142">To run the application:</span></span>
1. <span data-ttu-id="2ff2c-143">Välj **Felsökning** -> **Starta utan felsökning**.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="2ff2c-144">Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="2ff2c-145">Om du har flera projekt i en Visual Studio-lösning, måste alla projekt i lösningen finnas i samma mapp som lösningen eller i någon av dess undermappar.</span><span class="sxs-lookup"><span data-stu-id="2ff2c-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="2ff2c-146">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2ff2c-146">Next steps</span></span>

<span data-ttu-id="2ff2c-147">Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="2ff2c-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
