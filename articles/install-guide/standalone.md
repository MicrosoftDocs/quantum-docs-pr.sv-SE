---
title: 'Utveckla med Q # kommando rads program'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426426"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="17be4-102">Utveckla med Q # kommando rads program</span><span class="sxs-lookup"><span data-stu-id="17be4-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="17be4-103">Q #-program kan köras på egen hand utan en driv rutin på ett värd språk som C#, F # eller python.</span><span class="sxs-lookup"><span data-stu-id="17be4-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="17be4-104">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="17be4-104">Pre-requisites</span></span>

- [<span data-ttu-id="17be4-105">.NET Core SDK 3,1 eller senare</span><span class="sxs-lookup"><span data-stu-id="17be4-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="17be4-106">Installation</span><span class="sxs-lookup"><span data-stu-id="17be4-106">Installation</span></span>

<span data-ttu-id="17be4-107">Även om du kan bygga Q #-kommando rads program i vilken IDE som helst, rekommenderar vi att du använder Visual Studio Code (VS Code) eller Visual Studio IDE för dina Q #-program.</span><span class="sxs-lookup"><span data-stu-id="17be4-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="17be4-108">Att utveckla i dessa verktyg ger till gång till omfattande funktioner.</span><span class="sxs-lookup"><span data-stu-id="17be4-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="17be4-109">Så här konfigurerar du VS-kod:</span><span class="sxs-lookup"><span data-stu-id="17be4-109">To configure VS Code:</span></span>

1. <span data-ttu-id="17be4-110">Ladda ned och installera [vs Code](https://code.visualstudio.com/download) (Windows, Linux och Mac).</span><span class="sxs-lookup"><span data-stu-id="17be4-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="17be4-111">Installera [Microsoft QDK for vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="17be4-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="17be4-112">Så här konfigurerar du Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="17be4-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="17be4-113">Ladda ned och installera [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 eller senare med arbets belastningen .net Core plattforms oberoende utveckling aktive rad.</span><span class="sxs-lookup"><span data-stu-id="17be4-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="17be4-114">Hämta och installera [Microsoft-QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="17be4-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="17be4-115">Utveckla med Q # med VS Code</span><span class="sxs-lookup"><span data-stu-id="17be4-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="17be4-116">Installera mallarna för Q #-projekt:</span><span class="sxs-lookup"><span data-stu-id="17be4-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="17be4-117">Öppen VS Code.</span><span class="sxs-lookup"><span data-stu-id="17be4-117">Open VS Code.</span></span>
2. <span data-ttu-id="17be4-118">Klicka på **Visa**  ->  **kommando palett**.</span><span class="sxs-lookup"><span data-stu-id="17be4-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="17be4-119">Välj **Q #: installera projektmallar**.</span><span class="sxs-lookup"><span data-stu-id="17be4-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="17be4-120">När **projektmallar har installerats** visas QDK som är redo att användas med dina egna program och bibliotek.</span><span class="sxs-lookup"><span data-stu-id="17be4-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="17be4-121">Så här skapar du ett nytt projekt:</span><span class="sxs-lookup"><span data-stu-id="17be4-121">To create a new project:</span></span>

1. <span data-ttu-id="17be4-122">Klicka på **Visa**  ->  **kommando palett** och välj **Q #: skapa nytt projekt**.</span><span class="sxs-lookup"><span data-stu-id="17be4-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="17be4-123">Klicka på **fristående konsol program**.</span><span class="sxs-lookup"><span data-stu-id="17be4-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="17be4-124">Navigera till platsen där du vill spara projektet och klicka på **skapa projekt**.</span><span class="sxs-lookup"><span data-stu-id="17be4-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="17be4-125">När projektet har skapats klickar du på **Öppna nytt projekt...** i det nedre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="17be4-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="17be4-126">Inspektera projektet.</span><span class="sxs-lookup"><span data-stu-id="17be4-126">Inspect the project.</span></span> <span data-ttu-id="17be4-127">Du bör se en käll fil med namnet `Program.qs` , som är ett Q #-program som definierar en enkel åtgärd för att skriva ut ett meddelande till-konsolen.</span><span class="sxs-lookup"><span data-stu-id="17be4-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="17be4-128">Så här kör du programmet:</span><span class="sxs-lookup"><span data-stu-id="17be4-128">To run the application:</span></span>
1. <span data-ttu-id="17be4-129">Klicka på **Terminal**-  ->  **ny terminal**.</span><span class="sxs-lookup"><span data-stu-id="17be4-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="17be4-130">Skriv i Terminal-prompten `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="17be4-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="17be4-131">Du bör se följande text i utdatafönstret `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="17be4-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="17be4-132">Arbets ytor med flera rotmappar stöds för närvarande inte av tillägget VS Code #.</span><span class="sxs-lookup"><span data-stu-id="17be4-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="17be4-133">Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.</span><span class="sxs-lookup"><span data-stu-id="17be4-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="17be4-134">Utveckla med Q # med Visual Studio</span><span class="sxs-lookup"><span data-stu-id="17be4-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="17be4-135">Verifiera din Visual Studio-installation genom att skapa ett Q #- `Hello World` program.</span><span class="sxs-lookup"><span data-stu-id="17be4-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="17be4-136">Så här skapar du ett nytt Q #-program:</span><span class="sxs-lookup"><span data-stu-id="17be4-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="17be4-137">Öppna Visual Studio och klicka på **fil**  ->  **nytt**  ->  **projekt**.</span><span class="sxs-lookup"><span data-stu-id="17be4-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="17be4-138">Skriv `Q#` i sökrutan, Välj **Q #-program** och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="17be4-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="17be4-139">Ange ett namn och en plats för ditt program och klicka på **skapa**.</span><span class="sxs-lookup"><span data-stu-id="17be4-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="17be4-140">Inspektera projektet.</span><span class="sxs-lookup"><span data-stu-id="17be4-140">Inspect the project.</span></span> <span data-ttu-id="17be4-141">Du bör se en käll fil med namnet `Program.qs` , som är ett Q #-program som definierar en enkel åtgärd för att skriva ut ett meddelande till-konsolen.</span><span class="sxs-lookup"><span data-stu-id="17be4-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="17be4-142">Så här kör du programmet:</span><span class="sxs-lookup"><span data-stu-id="17be4-142">To run the application:</span></span>
1. <span data-ttu-id="17be4-143">Välj **fel söknings**  ->  **Start utan fel sökning**.</span><span class="sxs-lookup"><span data-stu-id="17be4-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="17be4-144">Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.</span><span class="sxs-lookup"><span data-stu-id="17be4-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="17be4-145">Om du har flera projekt i en Visual Studio-lösning måste alla projekt som finns i lösningen finnas i samma mapp som lösningen eller i en av dess undermappar.</span><span class="sxs-lookup"><span data-stu-id="17be4-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="17be4-146">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="17be4-146">Next steps</span></span>

<span data-ttu-id="17be4-147">Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="17be4-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
