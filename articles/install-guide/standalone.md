---
title: 'Köra Q #-program utan en driv rutin och ett värd språk'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706809"
---
# <a name="q-command-line-applications"></a><span data-ttu-id="d7722-102">Q # kommando rads program</span><span class="sxs-lookup"><span data-stu-id="d7722-102">Q# Command Line Applications</span></span>

<span data-ttu-id="d7722-103">Q #-program kan köras på egen hand utan en driv rutin på ett värd språk som C#, F # eller python.</span><span class="sxs-lookup"><span data-stu-id="d7722-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="d7722-104">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="d7722-104">Pre-requisites</span></span>

- [<span data-ttu-id="d7722-105">.NET Core SDK 3,1 eller senare</span><span class="sxs-lookup"><span data-stu-id="d7722-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="d7722-106">Installation</span><span class="sxs-lookup"><span data-stu-id="d7722-106">Installation</span></span>

<span data-ttu-id="d7722-107">Även om du kan bygga Q #-kommando rads program i vilken IDE som helst, rekommenderar vi starkt att du använder Visual Studio Code (VS Code) eller Visual Studio IDE för dina Q #-program.</span><span class="sxs-lookup"><span data-stu-id="d7722-107">While you can build Q# command line applications in any IDE, we highly recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="d7722-108">Genom att använda VS Code eller Visual Studio och QDK Visual Studio Code-tillägget får du till gång till mer avancerade funktioner.</span><span class="sxs-lookup"><span data-stu-id="d7722-108">By using VS Code or Visual Studio and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

- <span data-ttu-id="d7722-109">Installera [vs Code](https://code.visualstudio.com/download) (Windows, Linux och Mac)</span><span class="sxs-lookup"><span data-stu-id="d7722-109">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
- <span data-ttu-id="d7722-110">Installera [QDK-tillägget för vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) eller</span><span class="sxs-lookup"><span data-stu-id="d7722-110">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OR</span></span>
- <span data-ttu-id="d7722-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, med arbetsbelastningen för .NET Core plattformsoberoende utveckling aktiverat</span><span class="sxs-lookup"><span data-stu-id="d7722-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>
- <span data-ttu-id="d7722-112">Ladda ned och installera [Visual Studio-tillägget](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="d7722-112">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="d7722-113">Utveckla med Q # med VS Code</span><span class="sxs-lookup"><span data-stu-id="d7722-113">Develop with Q# using VS Code</span></span>

<span data-ttu-id="d7722-114">Installera Quantum-projektmallarna:</span><span class="sxs-lookup"><span data-stu-id="d7722-114">Install the Quantum project templates:</span></span>

- <span data-ttu-id="d7722-115">Gå till **Visa** -> **kommando palett**</span><span class="sxs-lookup"><span data-stu-id="d7722-115">Go to **View** -> **Command Palette**</span></span>
- <span data-ttu-id="d7722-116">Välj **Q #: installera projektmallar**</span><span class="sxs-lookup"><span data-stu-id="d7722-116">Select **Q#: Install project templates**</span></span>

<span data-ttu-id="d7722-117">Du har nu installerat Quantum Development Kit och kan börja använda det i dina egna program och bibliotek.</span><span class="sxs-lookup"><span data-stu-id="d7722-117">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>
- <span data-ttu-id="d7722-118">Skapa ett nytt projekt:</span><span class="sxs-lookup"><span data-stu-id="d7722-118">Create a new project:</span></span>
  - <span data-ttu-id="d7722-119">Gå till **Visa** -> **kommando palett**</span><span class="sxs-lookup"><span data-stu-id="d7722-119">Go to **View** -> **Command Palette**</span></span>
  - <span data-ttu-id="d7722-120">Välj **Q #: skapa nytt projekt**</span><span class="sxs-lookup"><span data-stu-id="d7722-120">Select **Q#: Create New Project**</span></span>
  - <span data-ttu-id="d7722-121">Välj **fristående konsol program**</span><span class="sxs-lookup"><span data-stu-id="d7722-121">Select **Standalone console application**</span></span>
  - <span data-ttu-id="d7722-122">Gå till den plats i filsystemet där du vill skapa programmet</span><span class="sxs-lookup"><span data-stu-id="d7722-122">Navigate to the location on the file system where you would like to create the application</span></span>
  - <span data-ttu-id="d7722-123">Klicka på knappen **Öppna nytt projekt...** när projektet har skapats</span><span class="sxs-lookup"><span data-stu-id="d7722-123">Click on the **Open new project...** button, once the project has been created</span></span>
        
- <span data-ttu-id="d7722-124">Inspektera projektet</span><span class="sxs-lookup"><span data-stu-id="d7722-124">Inspect the project</span></span>
  - <span data-ttu-id="d7722-125">Du bör se att en fil som `Program.qs` heter skapad, som är ett Q #-program som definierar en enkel åtgärd för att skriva ut ett meddelande till-konsolen.</span><span class="sxs-lookup"><span data-stu-id="d7722-125">You should see that a file called `Program.qs` created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="d7722-126">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="d7722-126">Run the application:</span></span>
  - <span data-ttu-id="d7722-127">Gå till **Terminal** -> ,**ny terminal**</span><span class="sxs-lookup"><span data-stu-id="d7722-127">Go to **Terminal** -> **New Terminal**</span></span>
  - <span data-ttu-id="d7722-128">Ange `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="d7722-128">Enter `dotnet run`</span></span>
  - <span data-ttu-id="d7722-129">Du bör se följande text i utdatafönstret `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="d7722-129">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="d7722-130">Arbetsytor med flera rotmappar stöds för närvarande inte av Visual Studio Code-tillägget.</span><span class="sxs-lookup"><span data-stu-id="d7722-130">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="d7722-131">Om du har flera projekt på en VS Code-arbetsyta, måste alla projekten finnas i samma rotmapp.</span><span class="sxs-lookup"><span data-stu-id="d7722-131">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="d7722-132">Utveckla med Q # med Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d7722-132">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="d7722-133">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="d7722-133">Verify the installation by creating a `Hello World` application</span></span>

- <span data-ttu-id="d7722-134">Skapa ett nytt Q#-program</span><span class="sxs-lookup"><span data-stu-id="d7722-134">Create a new Q# application</span></span>
  - <span data-ttu-id="d7722-135">Gå till **filen** -> **nytt** -> **projekt**</span><span class="sxs-lookup"><span data-stu-id="d7722-135">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="d7722-136">Skriv `Q#` i sökrutan</span><span class="sxs-lookup"><span data-stu-id="d7722-136">Type `Q#` in the search box</span></span>
  - <span data-ttu-id="d7722-137">Välj **Q#-program**</span><span class="sxs-lookup"><span data-stu-id="d7722-137">Select **Q# Application**</span></span>
  - <span data-ttu-id="d7722-138">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="d7722-138">Select **Next**</span></span>
  - <span data-ttu-id="d7722-139">Välj ett namn och en plats för ditt program</span><span class="sxs-lookup"><span data-stu-id="d7722-139">Choose a name and location for your application</span></span>
  - <span data-ttu-id="d7722-140">Välj **skapa**</span><span class="sxs-lookup"><span data-stu-id="d7722-140">Select **Create**</span></span>

- <span data-ttu-id="d7722-141">Inspektera projektet</span><span class="sxs-lookup"><span data-stu-id="d7722-141">Inspect the project</span></span>
  - <span data-ttu-id="d7722-142">Du bör se att en fil som `Program.qs` heter har skapats, som är ett Q #-program som definierar en enkel åtgärd för att skriva ut ett meddelande till-konsolen.</span><span class="sxs-lookup"><span data-stu-id="d7722-142">You should see that a file called `Program.qs` has been created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="d7722-143">Köra appen</span><span class="sxs-lookup"><span data-stu-id="d7722-143">Run the application</span></span>
  - <span data-ttu-id="d7722-144">Välj **fel söknings** -> **Start utan fel sökning**</span><span class="sxs-lookup"><span data-stu-id="d7722-144">Select **Debug** -> **Start Without Debugging**</span></span>
  - <span data-ttu-id="d7722-145">Du bör se att texten `Hello quantum world!` skrivs till ett konsolfönster.</span><span class="sxs-lookup"><span data-stu-id="d7722-145">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="d7722-146">Om du har flera projekt i en Visual Studio-lösning måste alla projekt i lösningen finnas i samma mapp som lösningen, eller i en av dess undermappar.</span><span class="sxs-lookup"><span data-stu-id="d7722-146">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  


## <a name="whats-next"></a><span data-ttu-id="d7722-147">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d7722-147">What's next?</span></span>

<span data-ttu-id="d7722-148">Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="d7722-148">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
