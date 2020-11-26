---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192918"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="29ef7-102">DrawRandomInt-åtgärd</span><span class="sxs-lookup"><span data-stu-id="29ef7-102">DrawRandomInt operation</span></span>

<span data-ttu-id="29ef7-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="29ef7-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="29ef7-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="29ef7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="29ef7-105">Ritar ett slumpmässigt heltal i ett angivet inklusivt intervall.</span><span class="sxs-lookup"><span data-stu-id="29ef7-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="29ef7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="29ef7-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="29ef7-107">min: [heltal](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="29ef7-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="29ef7-108">Det minsta heltal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="29ef7-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="29ef7-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="29ef7-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="29ef7-110">Det största heltal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="29ef7-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="29ef7-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="29ef7-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="29ef7-112">Ett heltal i mängd intervallet från `min` till `max` med enhetlig sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="29ef7-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="29ef7-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="29ef7-113">Remarks</span></span>

<span data-ttu-id="29ef7-114">Miss lyckas om `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="29ef7-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="29ef7-115">Se även</span><span class="sxs-lookup"><span data-stu-id="29ef7-115">See Also</span></span>

- [<span data-ttu-id="29ef7-116">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="29ef7-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)