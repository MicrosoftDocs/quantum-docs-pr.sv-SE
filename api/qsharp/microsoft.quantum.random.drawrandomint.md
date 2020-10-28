---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733595"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="3620e-102">DrawRandomInt-åtgärd</span><span class="sxs-lookup"><span data-stu-id="3620e-102">DrawRandomInt operation</span></span>

<span data-ttu-id="3620e-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3620e-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3620e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3620e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3620e-105">Ritar ett slumpmässigt heltal i ett angivet inklusivt intervall.</span><span class="sxs-lookup"><span data-stu-id="3620e-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="3620e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3620e-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="3620e-107">min: [heltal](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3620e-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3620e-108">Det minsta heltal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="3620e-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="3620e-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3620e-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3620e-110">Det största heltal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="3620e-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="3620e-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3620e-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3620e-112">Ett heltal i mängd intervallet från `min` till `max` med enhetlig sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="3620e-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="3620e-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3620e-113">Remarks</span></span>

<span data-ttu-id="3620e-114">Miss lyckas om `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="3620e-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3620e-115">Se även</span><span class="sxs-lookup"><span data-stu-id="3620e-115">See Also</span></span>

- [<span data-ttu-id="3620e-116">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="3620e-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)