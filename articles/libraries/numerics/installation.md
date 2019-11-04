---
title: Installation och validering av numeriska bibliotek | Microsoft Docs
description: Installation och validering av numeriska bibliotek
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 8369a6f342ee8e6f56b69bd1f2ce3df40e4093aa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184635"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="dab12-103">Installation och validering av numeriska bibliotek</span><span class="sxs-lookup"><span data-stu-id="dab12-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="dab12-104">Quantum Development Kit har stöd för numeriska funktioner via [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet-paketet.</span><span class="sxs-lookup"><span data-stu-id="dab12-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="dab12-105">**Visual Studio-> = 2019:** Om du använder Visual Studio 2019 eller senare kan du lägga till det numeriska paketet med hjälp av NuGet Package Manager.</span><span class="sxs-lookup"><span data-stu-id="dab12-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="dab12-106">Det gör du genom att välja "hantera NuGet-paket..." från meny alternativet "Project" i Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dab12-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="dab12-107">På fliken Bläddra söker du efter paket namnet "Microsoft. Quantum. numeric"</span><span class="sxs-lookup"><span data-stu-id="dab12-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="dab12-108">Se till att kryssa för "inkludera för hands version"</span><span class="sxs-lookup"><span data-stu-id="dab12-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="dab12-109">Detta visar de paket som är tillgängliga för nedladdning.</span><span class="sxs-lookup"><span data-stu-id="dab12-109">This will list the packages available for download.</span></span>
<span data-ttu-id="dab12-110">Om du hovrar över "Microsoft. Quantum. numeric", visar en nedåtriktad pil till höger om versions numret.</span><span class="sxs-lookup"><span data-stu-id="dab12-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="dab12-111">Klicka på pilen för att installera det numeriska paketet.</span><span class="sxs-lookup"><span data-stu-id="dab12-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="dab12-112">Mer information finns i UI- [guiden för paket hanteraren](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="dab12-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="dab12-113">Du kan också använda Package Manager-konsolen för att lägga till ett numeriskt bibliotek i projektet via kommando rads gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="dab12-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="dab12-114">Kör följande från Package Manager-konsolen:</span><span class="sxs-lookup"><span data-stu-id="dab12-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="dab12-115">Mer information finns i Guide till [Package Manager-konsolen](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="dab12-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="dab12-116">**Kommando rad eller Visual Studio Code:** Med hjälp av kommando raden i sin egen eller från Visual Studio Code, kan du använda kommandot `dotnet` för att lägga till NuGet-paket referens i projektet:</span><span class="sxs-lookup"><span data-stu-id="dab12-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```bash
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="dab12-117">Verifiera installationen</span><span class="sxs-lookup"><span data-stu-id="dab12-117">Verifying your installation</span></span>

<span data-ttu-id="dab12-118">Precis som resten av Quantum Development Kit, innehåller det numeriska biblioteket exempel som hjälper dig att komma igång så snabbt som möjligt.</span><span class="sxs-lookup"><span data-stu-id="dab12-118">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="dab12-119">Om du vill testa installationen med hjälp av dessa exempel klonar du [huvud exempel lagrings platsen](https://github.com/Microsoft/Quantum) och kör sedan ett av exemplen.</span><span class="sxs-lookup"><span data-stu-id="dab12-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="dab12-120">Så här kör du [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) exemplet:</span><span class="sxs-lookup"><span data-stu-id="dab12-120">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics/CustomModAdd
dotnet run
```