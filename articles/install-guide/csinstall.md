---
title: Utveckla med Q# och C#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 5bcb036b0b32e64d43f90e9a068d9dcc237890ba
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680167"
---
# <a name="using-q-with-c-and-f"></a><span data-ttu-id="2e008-102">Använda Q # med C\# och F\#</span><span class="sxs-lookup"><span data-stu-id="2e008-102">Using Q# with C\# and F\#</span></span>

<span data-ttu-id="2e008-103">Q # är utformat för att spelas upp bra med .NET-språk som C# och F #.</span><span class="sxs-lookup"><span data-stu-id="2e008-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="2e008-104">I den här guiden visar vi hur du använder Q # med ett värd program skrivet på ett .NET-språk.</span><span class="sxs-lookup"><span data-stu-id="2e008-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2e008-105">Krav</span><span class="sxs-lookup"><span data-stu-id="2e008-105">Prerequisites</span></span>

- <span data-ttu-id="2e008-106">Installera Quantum Development Kit [för användning med kommando rads projekt i Q #](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="2e008-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="2e008-107">Skapa ett Q #-bibliotek och en .NET-värd</span><span class="sxs-lookup"><span data-stu-id="2e008-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="2e008-108">Det första steget är att skapa projekt för ditt Q #-bibliotek och för den .NET-värd som ska anropa de åtgärder och funktioner som definierats i ditt Q #-bibliotek.</span><span class="sxs-lookup"><span data-stu-id="2e008-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="2e008-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2e008-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="2e008-110">Skapa ett nytt Q #-bibliotek</span><span class="sxs-lookup"><span data-stu-id="2e008-110">Create a new Q# library</span></span>
  - <span data-ttu-id="2e008-111">Gå till **filen** -> **nytt** -> **projekt**</span><span class="sxs-lookup"><span data-stu-id="2e008-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="2e008-112">Skriv "Q #" i sökrutan</span><span class="sxs-lookup"><span data-stu-id="2e008-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="2e008-113">Välj **Q #-bibliotek**</span><span class="sxs-lookup"><span data-stu-id="2e008-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="2e008-114">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="2e008-114">Select **Next**</span></span>
  - <span data-ttu-id="2e008-115">Välj ett namn och en plats för ditt bibliotek</span><span class="sxs-lookup"><span data-stu-id="2e008-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="2e008-116">Se till att "placera projektet och lösningen i samma katalog" är **avmarkerat**</span><span class="sxs-lookup"><span data-stu-id="2e008-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="2e008-117">Välj **skapa**</span><span class="sxs-lookup"><span data-stu-id="2e008-117">Select **Create**</span></span>
- <span data-ttu-id="2e008-118">Skapa ett nytt C#-eller F #-värd program</span><span class="sxs-lookup"><span data-stu-id="2e008-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="2e008-119">Gå till **Arkiv** → **nytt** → **projekt**</span><span class="sxs-lookup"><span data-stu-id="2e008-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="2e008-120">Välj "konsol program (.NET Core") "för antingen C# eller F #</span><span class="sxs-lookup"><span data-stu-id="2e008-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="2e008-121">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="2e008-121">Select **Next**</span></span>
  - <span data-ttu-id="2e008-122">Under *lösning*väljer du "Lägg till i lösning"</span><span class="sxs-lookup"><span data-stu-id="2e008-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="2e008-123">Välj ett namn för värd programmet</span><span class="sxs-lookup"><span data-stu-id="2e008-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="2e008-124">Välj **skapa**</span><span class="sxs-lookup"><span data-stu-id="2e008-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="2e008-125">Visual Studio-kod eller kommando rad</span><span class="sxs-lookup"><span data-stu-id="2e008-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="2e008-126">Skapa ett nytt Q #-bibliotek</span><span class="sxs-lookup"><span data-stu-id="2e008-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="2e008-127">Skapa ett nytt C#-eller F #-konsol projekt</span><span class="sxs-lookup"><span data-stu-id="2e008-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="2e008-128">Lägg till ditt Q #-bibliotek som en referens från värd programmet</span><span class="sxs-lookup"><span data-stu-id="2e008-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="2e008-129">Valfritt Skapa en lösning för båda projekten</span><span class="sxs-lookup"><span data-stu-id="2e008-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="2e008-130">Anrop till Q # från .NET</span><span class="sxs-lookup"><span data-stu-id="2e008-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="2e008-131">När du har skapat dina projekt enligt anvisningarna ovan kan du anropa i Q # från ditt .NET-konsol program.</span><span class="sxs-lookup"><span data-stu-id="2e008-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="2e008-132">I Q #-kompilatorn skapas .NET-klasser för varje Q #-åtgärd och-funktion som gör att du kan köra dina Quantum-program på en simulator.</span><span class="sxs-lookup"><span data-stu-id="2e008-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="2e008-133">Exempel på .net- [interoperabilitet](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) innehåller följande exempel på en Q #-åtgärd:</span><span class="sxs-lookup"><span data-stu-id="2e008-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="2e008-134">Om du vill anropa den här åtgärden från .NET på en Quantum-simulator kan `Run` du använda metoden `RunAlgorithm` för .net-klassen som genereras av Q #-kompilatorn:</span><span class="sxs-lookup"><span data-stu-id="2e008-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="2e008-135">C #</span><span class="sxs-lookup"><span data-stu-id="2e008-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="2e008-136">F#</span><span class="sxs-lookup"><span data-stu-id="2e008-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a><span data-ttu-id="2e008-137">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2e008-137">What's next?</span></span>

<span data-ttu-id="2e008-138">Nu när du har Quantum Development Kit konfigurerat för både Q # kommando rads program och för interoperabilitet med .NET, kan du skriva och köra [ditt första Quantum-program](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="2e008-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
