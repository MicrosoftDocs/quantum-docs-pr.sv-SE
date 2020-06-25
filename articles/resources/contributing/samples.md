---
title: Bidrags exempel till Microsoft QDK
description: Lär dig hur du bidrar med exempel kod till Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275393"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="61c08-103">Bidra till exempel i Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="61c08-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="61c08-104">Om du är intresse rad av att bidra med kod till [exempel lagrings platsen](https://github.com/Microsoft/Quantum), tack för att du gör miljön Quantum Development en bättre plats!</span><span class="sxs-lookup"><span data-stu-id="61c08-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="61c08-105">Exempel databasen för Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="61c08-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="61c08-106">För att hjälpa dig att förbereda ditt bidrag för att få ut så mycket som möjligt, är det bra att ta en titt på hur lagrings platsen upprättas:</span><span class="sxs-lookup"><span data-stu-id="61c08-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

<span data-ttu-id="61c08-107">Det vill säga att exemplen i [Microsoft/Quantum-lagringsplatsen](https://github.com/microsoft/Quantum) är uppdelade efter ämnes område i olika mappar som `algorithms/` , `arithmetic/` eller `characterization/` .</span><span class="sxs-lookup"><span data-stu-id="61c08-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="61c08-108">I mappen för varje ämnes område består varje exempel av en enda mapp som samlar in allt som en användare behöver för att utforska och använda det exemplet.</span><span class="sxs-lookup"><span data-stu-id="61c08-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="61c08-109">Hur exempel struktureras</span><span class="sxs-lookup"><span data-stu-id="61c08-109">How Samples are Structured</span></span>

<span data-ttu-id="61c08-110">Vi tittar på de filer som utgör varje mapp, låt oss ta en titt på [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) exemplet.</span><span class="sxs-lookup"><span data-stu-id="61c08-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="61c08-111">Fil</span><span class="sxs-lookup"><span data-stu-id="61c08-111">File</span></span>              | <span data-ttu-id="61c08-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="61c08-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="61c08-113">Q #-projekt som används för att bygga exemplet med .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="61c08-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="61c08-114">Q #-åtgärder och-funktioner för exemplet</span><span class="sxs-lookup"><span data-stu-id="61c08-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="61c08-115">C#-värd program som används för att köra exemplet</span><span class="sxs-lookup"><span data-stu-id="61c08-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="61c08-116">Python-värdprogram som används för att köra exemplet</span><span class="sxs-lookup"><span data-stu-id="61c08-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="61c08-117">Dokumentation om vad exemplet gör och hur det används</span><span class="sxs-lookup"><span data-stu-id="61c08-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="61c08-118">Alla exempel har inte exakt samma uppsättning filer (t. ex. vissa exempel kan vara C#-endast, andra kanske inte har en python-värd, eller så kan vissa exempel kräva att auxillary-datafiler fungerar).</span><span class="sxs-lookup"><span data-stu-id="61c08-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="61c08-119">Beskrivning av en användbar README-fil</span><span class="sxs-lookup"><span data-stu-id="61c08-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="61c08-120">En särskilt viktig fil, men är `README.md` filen, eftersom det är det som användarna behöver för att komma igång med ditt exempel!</span><span class="sxs-lookup"><span data-stu-id="61c08-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="61c08-121">Varje `README.md` ska börja med vissa metadata som hjälper docs.Microsoft.com/samples att hitta ditt bidrag.</span><span class="sxs-lookup"><span data-stu-id="61c08-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="61c08-122">Se hur chsh-spel återges</span><span class="sxs-lookup"><span data-stu-id="61c08-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="61c08-123">Dessa metadata tillhandahålls som ett [yaml-huvud](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) som anger vilka språk som exemplet täcker (vanligt vis är detta, `qsharp` `csharp` och `python` ) och vilka produkter som exemplet täcker (vanligt vis `qdk` ).</span><span class="sxs-lookup"><span data-stu-id="61c08-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="61c08-124">`page_type: sample`Nyckeln i rubriken krävs för att exemplet ska visas på docs.Microsoft.com/samples.</span><span class="sxs-lookup"><span data-stu-id="61c08-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="61c08-125">På samma sätt `product` är och `language` nycklarna kritiska för att hjälpa användarna att hitta och köra ditt exempel.</span><span class="sxs-lookup"><span data-stu-id="61c08-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="61c08-126">Därefter är det bra att ge en kort introduktion som säger vad ditt nya exempel gör:</span><span class="sxs-lookup"><span data-stu-id="61c08-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="61c08-127">Användare av exemplet kommer också att uppskatta vad de behöver för att köra det (t. ex.: användare behöver bara själva Quantum Development Kit eller behöver de ytterligare program vara som node.js?):</span><span class="sxs-lookup"><span data-stu-id="61c08-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="61c08-128">Med allt det på plats kan du tala om för användarna hur de ska köra exemplet:</span><span class="sxs-lookup"><span data-stu-id="61c08-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="61c08-129">Slutligen är det bra att berätta för användarna vad varje fil i exemplet gör och var de kan gå till mer information:</span><span class="sxs-lookup"><span data-stu-id="61c08-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="61c08-130">Se till att använda absoluta URL: er här eftersom exemplet visas på en annan URL när du återger på docs.microsoft.com/samples!</span><span class="sxs-lookup"><span data-stu-id="61c08-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
