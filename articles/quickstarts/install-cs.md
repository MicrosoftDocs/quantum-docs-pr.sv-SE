---
title: Utveckla med Q# och .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 13d73bdf0287941c89e03ba63869095e5fca4e70
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867564"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="bf116-102">Utveckla med Q# och .NET</span><span class="sxs-lookup"><span data-stu-id="bf116-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="bf116-103">Q# är utformat att fungera med .NET-språk som C# och F# .</span><span class="sxs-lookup"><span data-stu-id="bf116-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="bf116-104">I den här guiden visar vi hur du använder Q# med ett värdprogram som skrivits i ett .NET-språk.</span><span class="sxs-lookup"><span data-stu-id="bf116-104">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="bf116-105">Först skapar vi Q#-programmet och .NET-värden, och sedan visar vi hur du anropar Q# från värden.</span><span class="sxs-lookup"><span data-stu-id="bf116-105">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bf116-106">Krav</span><span class="sxs-lookup"><span data-stu-id="bf116-106">Prerequisites</span></span>

- <span data-ttu-id="bf116-107">Installera Quantum Development Kit [för användning med kommandoradsprojekt i Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="bf116-107">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="bf116-108">Skapa ett Q#-bibliotek och en .NET-värd</span><span class="sxs-lookup"><span data-stu-id="bf116-108">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="bf116-109">Det första steget är att skapa projekt för ditt Q#-bibliotek och för den .NET-värd som ska anropa åtgärder och funktioner som definierats i ditt Q#-bibliotek.</span><span class="sxs-lookup"><span data-stu-id="bf116-109">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="bf116-110">Följ anvisningarna på den flik som motsvarar din utvecklingsmiljö.</span><span class="sxs-lookup"><span data-stu-id="bf116-110">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="bf116-111">Om du använder ett annat redigeringsprogram än Visual Studio eller VS Code följer du bara stegen för kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="bf116-111">If you are using an editor other than Visual Studio or VS Code, simply follow the command line steps.</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="bf116-112">Visual Studio Code eller kommandorad</span><span class="sxs-lookup"><span data-stu-id="bf116-112">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="bf116-113">Skapa ett nytt Q#-bibliotek</span><span class="sxs-lookup"><span data-stu-id="bf116-113">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="bf116-114">Skapa ett nytt C#- eller F#-konsolprojekt</span><span class="sxs-lookup"><span data-stu-id="bf116-114">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="bf116-115">Lägg till ditt Q#-bibliotek som en referens från värdprogrammet</span><span class="sxs-lookup"><span data-stu-id="bf116-115">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="bf116-116">[Valfritt] Skapa en lösning för båda projekten</span><span class="sxs-lookup"><span data-stu-id="bf116-116">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="bf116-117">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="bf116-117">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="bf116-118">Skapa ett nytt Q#-bibliotek</span><span class="sxs-lookup"><span data-stu-id="bf116-118">Create a new Q# library</span></span>
  - <span data-ttu-id="bf116-119">Gå till **Arkiv** -> **Nytt** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="bf116-119">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="bf116-120">Skriv "Q#" i sökrutan</span><span class="sxs-lookup"><span data-stu-id="bf116-120">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="bf116-121">Välj **Q#-bibliotek**</span><span class="sxs-lookup"><span data-stu-id="bf116-121">Select **Q# Library**</span></span>
  - <span data-ttu-id="bf116-122">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="bf116-122">Select **Next**</span></span>
  - <span data-ttu-id="bf116-123">Välj ett namn och en plats för ditt bibliotek</span><span class="sxs-lookup"><span data-stu-id="bf116-123">Choose a name and location for your library</span></span>
  - <span data-ttu-id="bf116-124">Kontrollera att ”Placera projektet och lösningen i samma katalog” är **avmarkerat**</span><span class="sxs-lookup"><span data-stu-id="bf116-124">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="bf116-125">Välj **Skapa**</span><span class="sxs-lookup"><span data-stu-id="bf116-125">Select **Create**</span></span>
- <span data-ttu-id="bf116-126">Skapa ett nytt C#- eller F#-värdprogram</span><span class="sxs-lookup"><span data-stu-id="bf116-126">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="bf116-127">Gå till **Arkiv** → **Nytt** → **Projekt**</span><span class="sxs-lookup"><span data-stu-id="bf116-127">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="bf116-128">Välj ”Konsolapp (.NET Core”)” för antingen C# eller F#</span><span class="sxs-lookup"><span data-stu-id="bf116-128">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="bf116-129">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="bf116-129">Select **Next**</span></span>
  - <span data-ttu-id="bf116-130">Under *Lösning*väljer du ”Lägg till i lösning”</span><span class="sxs-lookup"><span data-stu-id="bf116-130">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="bf116-131">Välj ett namn på värdprogrammet</span><span class="sxs-lookup"><span data-stu-id="bf116-131">Choose a name for your host program</span></span>
  - <span data-ttu-id="bf116-132">Välj **Skapa**</span><span class="sxs-lookup"><span data-stu-id="bf116-132">Select **Create**</span></span>

***

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="bf116-133">Anropa till Q# från .NET</span><span class="sxs-lookup"><span data-stu-id="bf116-133">Calling into Q# from .NET</span></span>

<span data-ttu-id="bf116-134">När du har konfigurerat dina projekt enligt anvisningarna ovan, kan du anropa Q# från ditt .NET-konsolprogram.</span><span class="sxs-lookup"><span data-stu-id="bf116-134">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="bf116-135">Q#-kompileraren skapar .NET-klasser för varje Q#-åtgärd och funktion, så att du kan köra kvantprogrammen i en simulator.</span><span class="sxs-lookup"><span data-stu-id="bf116-135">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="bf116-136">[I exemplet på .NET-interoperabilitet](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) finns följande exempel på en Q#-åtgärd:</span><span class="sxs-lookup"><span data-stu-id="bf116-136">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="bf116-137">Om du vill anropa den här åtgärden från .NET i en kvantsimulator, kan du använda `Run`-metoden för den `RunAlgorithm`-.NET-klass som genererades av Q#-kompileraren:</span><span class="sxs-lookup"><span data-stu-id="bf116-137">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="bf116-138">C#</span><span class="sxs-lookup"><span data-stu-id="bf116-138">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="bf116-139">F#</span><span class="sxs-lookup"><span data-stu-id="bf116-139">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="bf116-140">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="bf116-140">Next steps</span></span>

<span data-ttu-id="bf116-141">Nu när du har konfigurerat Quantum Development Kit för både Q#-kommandoradsprogram och för interoperabilitet med .NET kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="bf116-141">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
