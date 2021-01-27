---
title: Utveckla med Q# och .NET
description: Lär dig hur du skapar ett Q#-program med .NET-språk.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: de79c361331766572f5608c341be766e071e01b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844311"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="7efe3-103">Utveckla med Q# och .NET</span><span class="sxs-lookup"><span data-stu-id="7efe3-103">Develop with Q# and .NET</span></span>

<span data-ttu-id="7efe3-104">Q# är utformat att fungera med .NET-språk som C# och F# .</span><span class="sxs-lookup"><span data-stu-id="7efe3-104">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="7efe3-105">I den här guiden visar vi hur du använder Q# med ett värdprogram som skrivits i ett .NET-språk.</span><span class="sxs-lookup"><span data-stu-id="7efe3-105">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="7efe3-106">Först skapar vi Q#-programmet och .NET-värden, och sedan visar vi hur du anropar Q# från värden.</span><span class="sxs-lookup"><span data-stu-id="7efe3-106">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7efe3-107">Krav</span><span class="sxs-lookup"><span data-stu-id="7efe3-107">Prerequisites</span></span>

- <span data-ttu-id="7efe3-108">Installera Quantum Development Kit [för användning med projekt i Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="7efe3-108">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="7efe3-109">Skapa ett Q#-bibliotek och en .NET-värd</span><span class="sxs-lookup"><span data-stu-id="7efe3-109">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="7efe3-110">Det första steget är att skapa projekt för ditt Q#-bibliotek och för den .NET-värd som ska anropa åtgärder och funktioner som definierats i ditt Q#-bibliotek.</span><span class="sxs-lookup"><span data-stu-id="7efe3-110">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="7efe3-111">Följ anvisningarna på den flik som motsvarar din utvecklingsmiljö.</span><span class="sxs-lookup"><span data-stu-id="7efe3-111">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="7efe3-112">Om du använder ett annat redigeringsprogram än Visual Studio eller VS Code följer du bara stegen för kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="7efe3-112">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="7efe3-113">Visual Studio Code eller kommandotolk</span><span class="sxs-lookup"><span data-stu-id="7efe3-113">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="7efe3-114">Skapa ett nytt Q#-bibliotek</span><span class="sxs-lookup"><span data-stu-id="7efe3-114">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="7efe3-115">Skapa ett nytt C#- eller F#-konsolprojekt</span><span class="sxs-lookup"><span data-stu-id="7efe3-115">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="7efe3-116">Lägg till ditt Q#-bibliotek som en referens från värdprogrammet</span><span class="sxs-lookup"><span data-stu-id="7efe3-116">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="7efe3-117">[Valfritt] Skapa en lösning för båda projekten</span><span class="sxs-lookup"><span data-stu-id="7efe3-117">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="7efe3-118">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="7efe3-118">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="7efe3-119">Skapa ett nytt Q#-bibliotek</span><span class="sxs-lookup"><span data-stu-id="7efe3-119">Create a new Q# library</span></span>
  - <span data-ttu-id="7efe3-120">Gå till **Arkiv** -> **Nytt** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="7efe3-120">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="7efe3-121">Skriv "Q#" i sökrutan</span><span class="sxs-lookup"><span data-stu-id="7efe3-121">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="7efe3-122">Välj **Q#-bibliotek**</span><span class="sxs-lookup"><span data-stu-id="7efe3-122">Select **Q# Library**</span></span>
  - <span data-ttu-id="7efe3-123">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="7efe3-123">Select **Next**</span></span>
  - <span data-ttu-id="7efe3-124">Välj ett namn och en plats för ditt bibliotek</span><span class="sxs-lookup"><span data-stu-id="7efe3-124">Choose a name and location for your library</span></span>
  - <span data-ttu-id="7efe3-125">Kontrollera att ”Placera projektet och lösningen i samma katalog” är **avmarkerat**</span><span class="sxs-lookup"><span data-stu-id="7efe3-125">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="7efe3-126">Välj **Skapa**</span><span class="sxs-lookup"><span data-stu-id="7efe3-126">Select **Create**</span></span>
- <span data-ttu-id="7efe3-127">Skapa ett nytt C#- eller F#-värdprogram</span><span class="sxs-lookup"><span data-stu-id="7efe3-127">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="7efe3-128">Gå till **Arkiv** → **Nytt** → **Projekt**</span><span class="sxs-lookup"><span data-stu-id="7efe3-128">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="7efe3-129">Välj ”Konsolapp (.NET Core”)” för antingen C# eller F#</span><span class="sxs-lookup"><span data-stu-id="7efe3-129">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="7efe3-130">Välj **Nästa**</span><span class="sxs-lookup"><span data-stu-id="7efe3-130">Select **Next**</span></span>
  - <span data-ttu-id="7efe3-131">Under *Lösning* väljer du ”Lägg till i lösning”</span><span class="sxs-lookup"><span data-stu-id="7efe3-131">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="7efe3-132">Välj ett namn på värdprogrammet</span><span class="sxs-lookup"><span data-stu-id="7efe3-132">Choose a name for your host program</span></span>
  - <span data-ttu-id="7efe3-133">Välj **Skapa**</span><span class="sxs-lookup"><span data-stu-id="7efe3-133">Select **Create**</span></span>

<span data-ttu-id="7efe3-134">\*\*_</span><span class="sxs-lookup"><span data-stu-id="7efe3-134">\*\*_</span></span>

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="7efe3-135">Anropa till Q# från .NET</span><span class="sxs-lookup"><span data-stu-id="7efe3-135">Calling into Q# from .NET</span></span>

<span data-ttu-id="7efe3-136">När du har konfigurerat dina projekt enligt anvisningarna ovan, kan du anropa Q# från ditt .NET-konsolprogram.</span><span class="sxs-lookup"><span data-stu-id="7efe3-136">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="7efe3-137">Q#-kompileraren skapar .NET-klasser för varje Q#-åtgärd och funktion, så att du kan köra kvantprogrammen i en simulator.</span><span class="sxs-lookup"><span data-stu-id="7efe3-137">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="7efe3-138">[I exemplet på .NET-interoperabilitet](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) finns följande exempel på en Q#-åtgärd:</span><span class="sxs-lookup"><span data-stu-id="7efe3-138">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="7efe3-139">Om du vill anropa den här åtgärden från .NET i en kvantsimulator, kan du använda `Run`-metoden för den `RunAlgorithm`-.NET-klass som genererades av Q#-kompileraren:</span><span class="sxs-lookup"><span data-stu-id="7efe3-139">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="7efe3-140">C#</span><span class="sxs-lookup"><span data-stu-id="7efe3-140">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="7efe3-141">F#</span><span class="sxs-lookup"><span data-stu-id="7efe3-141">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

<span data-ttu-id="7efe3-142">_\*\*</span><span class="sxs-lookup"><span data-stu-id="7efe3-142">_\*\*</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="7efe3-143">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="7efe3-143">Next steps</span></span>

<span data-ttu-id="7efe3-144">Nu när du har konfigurerat Quantum Development Kit för både Q#-program och interoperabilitet med .NET kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="7efe3-144">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
