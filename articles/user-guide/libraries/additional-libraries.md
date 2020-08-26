---
title: Använda ytterligare Q# bibliotek
description: Lär dig hur du lägger till ytterligare Q# bibliotek i dina Quantum-program.
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: c558e25bf0d906ba6480cd7c41d3ece4ea97c2d1
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863075"
---
# <a name="using-additional-no-locq-libraries"></a><span data-ttu-id="787af-103">Använda ytterligare Q# bibliotek</span><span class="sxs-lookup"><span data-stu-id="787af-103">Using Additional Q# Libraries</span></span>

<span data-ttu-id="787af-104">Quantum Development Kit innehåller ytterligare domänfunktionalitet med _NuGet-paket_ som kan läggas till i dina Q# projekt.</span><span class="sxs-lookup"><span data-stu-id="787af-104">The Quantum Development Kit provides additional domain-specific functionality through _NuGet packages_ that can be added to your Q# projects.</span></span>

| <span data-ttu-id="787af-105">Q# Bibliotek</span><span class="sxs-lookup"><span data-stu-id="787af-105">Q# Library</span></span>  | <span data-ttu-id="787af-106">NuGet-paket</span><span class="sxs-lookup"><span data-stu-id="787af-106">NuGet package</span></span> | <span data-ttu-id="787af-107">Anteckningar</span><span class="sxs-lookup"><span data-stu-id="787af-107">Notes</span></span> |
|---------|---------|--------|
| [<span data-ttu-id="787af-108">Q# standard bibliotek</span><span class="sxs-lookup"><span data-stu-id="787af-108">Q# standard library</span></span>](xref:microsoft.quantum.libraries.standard.intro) | [<span data-ttu-id="787af-109">**Microsoft. Quantum. standard**</span><span class="sxs-lookup"><span data-stu-id="787af-109">**Microsoft.Quantum.Standard**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | <span data-ttu-id="787af-110">Ingår som standard</span><span class="sxs-lookup"><span data-stu-id="787af-110">Included by default</span></span> |
| [<span data-ttu-id="787af-111">Bibliotek för kvantkemi</span><span class="sxs-lookup"><span data-stu-id="787af-111">Quantum chemistry library</span></span>](xref:microsoft.quantum.chemistry.concepts.intro) | [<span data-ttu-id="787af-112">**Microsoft.Quantum.Chemistry**</span><span class="sxs-lookup"><span data-stu-id="787af-112">**Microsoft.Quantum.Chemistry**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [<span data-ttu-id="787af-113">Bibliotek för kvantmatematik</span><span class="sxs-lookup"><span data-stu-id="787af-113">Quantum numerics library</span></span>](xref:microsoft.quantum.numerics.intro) | [<span data-ttu-id="787af-114">**Microsoft. Quantum. numeric**</span><span class="sxs-lookup"><span data-stu-id="787af-114">**Microsoft.Quantum.Numerics**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [<span data-ttu-id="787af-115">Bibliotek för kvantmaskininlärning</span><span class="sxs-lookup"><span data-stu-id="787af-115">Quantum machine learning library</span></span>](xref:microsoft.quantum.libraries.machine-learning.intro) | [<span data-ttu-id="787af-116">**Microsoft.Quantum.MachineLearning**</span><span class="sxs-lookup"><span data-stu-id="787af-116">**Microsoft.Quantum.MachineLearning**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

<span data-ttu-id="787af-117">När du har installerat Quantum Development Kit för användning med din önskade miljö och ditt värd språk kan du enkelt lägga till bibliotek i enskilda Q# projekt utan någon ytterligare installation.</span><span class="sxs-lookup"><span data-stu-id="787af-117">Once you have installed the Quantum Development Kit for use with your preferred environment and host language, you can easily add libraries to individual Q# projects without any further installation.</span></span>

> [!NOTE]
> <span data-ttu-id="787af-118">Vissa Q# bibliotek kan fungera bra med ytterligare verktyg som fungerar tillsammans Q# med dina program eller som integreras med dina värd program.</span><span class="sxs-lookup"><span data-stu-id="787af-118">Some Q# libraries may work well with additional tools that work alongside your Q# programs, or that integrate with your host applications.</span></span>
> <span data-ttu-id="787af-119">[Installations anvisningarna för kemi Library](xref:microsoft.quantum.chemistry.concepts.installation) beskriver till exempel hur du använder [ **Microsoft. Quantum. kemi** -paketet](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) tillsammans med NWChem-plattformen för beräknings kemi och hur du installerar `qdk-chem` kommando rads verktygen för att arbeta med Quantum kemi-data.</span><span class="sxs-lookup"><span data-stu-id="787af-119">For example, the [chemistry library installation instructions](xref:microsoft.quantum.chemistry.concepts.installation) describe how to use the [**Microsoft.Quantum.Chemistry** package](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) together with the NWChem computational chemistry platform, and how to install the `qdk-chem` command-line tools for working with quantum chemistry data.</span></span>

## <a name="no-locq-applications-or-net-interopability"></a>[<span data-ttu-id="787af-120">Q# program eller .NET-interop</span><span class="sxs-lookup"><span data-stu-id="787af-120">Q# applications or .NET interopability</span></span>](#tab/tabid-csproj)

<span data-ttu-id="787af-121">**Kommando tolk eller Visual Studio-kod:** Med hjälp av kommando tolken på egen hand eller i Visual Studio Code kan du använda `dotnet` kommandot för att lägga till en NuGet-paket referens i projektet.</span><span class="sxs-lookup"><span data-stu-id="787af-121">**Command prompt or Visual Studio Code:** Using the command prompt on its own or from within Visual Studio Code, you can use the `dotnet` command to add a NuGet package reference to your project.</span></span>
<span data-ttu-id="787af-122">Om du till exempel vill lägga till paketet [**Microsoft. Quantum. numeric**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="787af-122">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

<span data-ttu-id="787af-123">**Visual Studio:** Om du använder Visual Studio 2019 eller senare kan du lägga till ytterligare Q# paket med NuGet Package Manager.</span><span class="sxs-lookup"><span data-stu-id="787af-123">**Visual Studio:** If you are using Visual Studio 2019 or later, you can add additional Q# packages using the NuGet Package Manager.</span></span>
<span data-ttu-id="787af-124">Så här läser du in ett paket:</span><span class="sxs-lookup"><span data-stu-id="787af-124">To load a package:</span></span> 
1. <span data-ttu-id="787af-125">Öppna ett projekt i Visual Studio och välj **Hantera NuGet-paket...** från **projekt** -menyn.</span><span class="sxs-lookup"><span data-stu-id="787af-125">With a project open in Visual Studio, select **Manage NuGet Packages...** from the **Project** menu.</span></span>

2. <span data-ttu-id="787af-126">Klicka på **Bläddra**, Välj **Inkludera för hands version** och Sök efter paket namnet "Microsoft. Quantum. numeric".</span><span class="sxs-lookup"><span data-stu-id="787af-126">Click **Browse**, select **Include prerelease** and search for the package name "Microsoft.Quantum.Numerics".</span></span> <span data-ttu-id="787af-127">Detta visar de paket som är tillgängliga för nedladdning.</span><span class="sxs-lookup"><span data-stu-id="787af-127">This will list the packages available for download.</span></span>

3. <span data-ttu-id="787af-128">Hovra över **Microsoft. Quantum. numeric** och klicka på pilen som pekar nedåt till höger om versions numret för att installera det numeriska paketet.</span><span class="sxs-lookup"><span data-stu-id="787af-128">Hover over **Microsoft.Quantum.Numerics** and click the downward-pointing arrow to the right of the version number to install the numerics package.</span></span>

<span data-ttu-id="787af-129">Mer information finns i UI- [guiden för paket hanteraren](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="787af-129">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="787af-130">Du kan också använda Package Manager-konsolen för att lägga till ett numeriskt bibliotek i projektet via kommando rads gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="787af-130">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Använda Package Manager-konsolen från kommando tolken](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="787af-132">Kör följande från Package Manager-konsolen:</span><span class="sxs-lookup"><span data-stu-id="787af-132">From the Package Manager Console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="787af-133">Mer information finns i Guide till [Package Manager-konsolen](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="787af-133">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

## <a name="ino-locq-notebooks"></a>[<span data-ttu-id="787af-134">I Q# antecknings böcker</span><span class="sxs-lookup"><span data-stu-id="787af-134">IQ# Notebooks</span></span>](#tab/tabid-notebook)

<span data-ttu-id="787af-135">Du kan göra ytterligare paket tillgängliga för användning i en I- Q# anteckningsbok med hjälp av [ `%package` kommandot Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="787af-135">You can make additional packages available for use in an IQ# Notebook by using the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="787af-136">Om du till exempel vill lägga till paketet [**Microsoft. Quantum. numeric**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) för användning I en i Q# -anteckningsbok, kör du följande kommando i en Notebook-cell:</span><span class="sxs-lookup"><span data-stu-id="787af-136">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following command in a notebook cell:</span></span>

```
%package Microsoft.Quantum.Numerics
```

<span data-ttu-id="787af-137">Efter det här kommandot är paketet tillgängligt för alla celler i antecknings boken.</span><span class="sxs-lookup"><span data-stu-id="787af-137">Following this command, the package is available to any cells within the notebook.</span></span>
<span data-ttu-id="787af-138">Om du vill göra paketet tillgängligt från Q# kod i den aktuella arbets ytan läser du in arbets ytan igen när du har lagt till ditt paket:</span><span class="sxs-lookup"><span data-stu-id="787af-138">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```
%workspace reload
```

## <a name="python-interoperability"></a>[<span data-ttu-id="787af-139">Python-interoperabilitet</span><span class="sxs-lookup"><span data-stu-id="787af-139">Python interoperability</span></span>](#tab/tabid-python)


<span data-ttu-id="787af-140">Du kan göra ytterligare paket tillgängliga för användning i ett python-värdprogram med hjälp av- [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) metoden.</span><span class="sxs-lookup"><span data-stu-id="787af-140">You can make additional packages available for use in a Python host program by using the [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) method.</span></span>
<span data-ttu-id="787af-141">Om du till exempel vill lägga till paketet [**Microsoft. Quantum. numeric**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) för användning I en i Q# -anteckningsbok kör du följande python-kod:</span><span class="sxs-lookup"><span data-stu-id="787af-141">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following Python code:</span></span>

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

<span data-ttu-id="787af-142">Efter det här kommandot kommer paketet att göras tillgängligt för all Q# kod som kompileras med `qsharp.compile` .</span><span class="sxs-lookup"><span data-stu-id="787af-142">Following this command, the package will be made available to any Q# code compiled using `qsharp.compile`.</span></span>
<span data-ttu-id="787af-143">Om du vill göra paketet tillgängligt från Q# kod i den aktuella arbets ytan läser du in arbets ytan igen när du har lagt till ditt paket:</span><span class="sxs-lookup"><span data-stu-id="787af-143">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```python
qsharp.reload()
```

***
