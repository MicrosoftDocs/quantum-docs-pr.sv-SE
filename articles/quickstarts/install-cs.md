---
title: Utveckla med Q# och .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 2b0b16bdd9fccc3b668036e6df2b20e11b32f8b6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274156"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="e8cda-102">Utveckla med Q# och .NET</span><span class="sxs-lookup"><span data-stu-id="e8cda-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="e8cda-103">Q# är utformat att fungera med .NET-språk som C# och F# .</span><span class="sxs-lookup"><span data-stu-id="e8cda-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="e8cda-104">I den här guiden visar vi hur du använder Q# med ett värdprogram skrivet med ett .NET-språk.</span><span class="sxs-lookup"><span data-stu-id="e8cda-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e8cda-105">Krav</span><span class="sxs-lookup"><span data-stu-id="e8cda-105">Prerequisites</span></span>

- <span data-ttu-id="e8cda-106">Installera Quantum Development Kit [för användning med kommandoradsprojekt i Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="e8cda-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="e8cda-107">Skapa ett Q#-bibliotek och en .NET-värd</span><span class="sxs-lookup"><span data-stu-id="e8cda-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="e8cda-108">Det första steget är att skapa projekt för ditt Q#-bibliotek och för den .NET-värd som ska anropa åtgärder och funktioner som definierats i ditt Q#-bibliotek.</span><span class="sxs-lookup"><span data-stu-id="e8cda-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="e8cda-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e8cda-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="e8cda-110">Skapa ett nytt Q#-bibliotek</span><span class="sxs-lookup"><span data-stu-id="e8cda-110">Create a new Q# library</span></span>
  - <span data-ttu-id="e8cda-111">Gå till **Arkiv** -> **Nytt** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="e8cda-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="e8cda-112">Skriv ”Q#” i sökrutan</span><span class="sxs-lookup"><span data-stu-id="e8cda-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="e8cda-113">Välj **Q#-bibliotek**</span><span class="sxs-lookup"><span data-stu-id="e8cda-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="e8cda-114">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="e8cda-114">Select **Next**</span></span>
  - <span data-ttu-id="e8cda-115">Välj ett namn och en plats för ditt bibliotek</span><span class="sxs-lookup"><span data-stu-id="e8cda-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="e8cda-116">Kontrollera att ”Placera projektet och lösningen i samma katalog” är **avmarkerat**</span><span class="sxs-lookup"><span data-stu-id="e8cda-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="e8cda-117">Välj **Skapa**</span><span class="sxs-lookup"><span data-stu-id="e8cda-117">Select **Create**</span></span>
- <span data-ttu-id="e8cda-118">Skapa ett nytt C#- eller F#-värdprogram</span><span class="sxs-lookup"><span data-stu-id="e8cda-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="e8cda-119">Gå till **Arkiv** → **Nytt** → **Projekt**</span><span class="sxs-lookup"><span data-stu-id="e8cda-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="e8cda-120">Välj ”Konsolapp (.NET Core”)” för antingen C# eller F#</span><span class="sxs-lookup"><span data-stu-id="e8cda-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="e8cda-121">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="e8cda-121">Select **Next**</span></span>
  - <span data-ttu-id="e8cda-122">Under *Lösning*väljer du ”Lägg till i lösning”</span><span class="sxs-lookup"><span data-stu-id="e8cda-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="e8cda-123">Välj ett namn på värdprogrammet</span><span class="sxs-lookup"><span data-stu-id="e8cda-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="e8cda-124">Välj **Skapa**</span><span class="sxs-lookup"><span data-stu-id="e8cda-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="e8cda-125">Visual Studio Code eller kommandorad</span><span class="sxs-lookup"><span data-stu-id="e8cda-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="e8cda-126">Skapa ett nytt Q#-bibliotek</span><span class="sxs-lookup"><span data-stu-id="e8cda-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="e8cda-127">Skapa ett nytt C#- eller F#-konsolprojekt</span><span class="sxs-lookup"><span data-stu-id="e8cda-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="e8cda-128">Lägg till ditt Q#-bibliotek som en referens från värdprogrammet</span><span class="sxs-lookup"><span data-stu-id="e8cda-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="e8cda-129">[Valfritt] Skapa en lösning för båda projekten</span><span class="sxs-lookup"><span data-stu-id="e8cda-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="e8cda-130">Anropa Q# från .NET</span><span class="sxs-lookup"><span data-stu-id="e8cda-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="e8cda-131">När du har konfigurerat dina projekt enligt anvisningarna ovan, kan du anropa Q# från ditt .NET-konsolprogram.</span><span class="sxs-lookup"><span data-stu-id="e8cda-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="e8cda-132">Q#-kompileraren skapar .NET-klasser för varje Q#-åtgärd och funktion, så att du kan köra kvantprogrammen i en simulator.</span><span class="sxs-lookup"><span data-stu-id="e8cda-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="e8cda-133">[I exemplet på .NET-interoperabilitet](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) visas följande Q#-åtgärd:</span><span class="sxs-lookup"><span data-stu-id="e8cda-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="e8cda-134">Om du vill anropa den här åtgärden från .NET i en kvantsimulator, kan du använda `Run`-metoden för den `RunAlgorithm`-.NET-klass som genererades av Q#-kompileraren:</span><span class="sxs-lookup"><span data-stu-id="e8cda-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="e8cda-135">C#</span><span class="sxs-lookup"><span data-stu-id="e8cda-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="e8cda-136">F#</span><span class="sxs-lookup"><span data-stu-id="e8cda-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="e8cda-137">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="e8cda-137">Next steps</span></span>

<span data-ttu-id="e8cda-138">Nu när du har konfigurerat Quantum Development Kit för både Q#-kommandoradsprogram och för interoperabilitet med .NET, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="e8cda-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
