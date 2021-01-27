---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851146"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="6f05a-102">DrawRandomInt-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6f05a-102">DrawRandomInt operation</span></span>

<span data-ttu-id="6f05a-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="6f05a-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="6f05a-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6f05a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6f05a-105">Ritar ett slumpmässigt heltal i ett angivet inklusivt intervall.</span><span class="sxs-lookup"><span data-stu-id="6f05a-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="6f05a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6f05a-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="6f05a-107">min: [heltal](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f05a-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6f05a-108">Det minsta heltal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="6f05a-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="6f05a-109">Max: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f05a-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6f05a-110">Det största heltal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="6f05a-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="6f05a-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f05a-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6f05a-112">Ett heltal i mängd intervallet från `min` till `max` med enhetlig sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="6f05a-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="6f05a-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="6f05a-113">Example</span></span>

<span data-ttu-id="6f05a-114">Följande Q #-kodfragment rullar slumpmässigt en sida med sex sidor:</span><span class="sxs-lookup"><span data-stu-id="6f05a-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a><span data-ttu-id="6f05a-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6f05a-115">Remarks</span></span>

<span data-ttu-id="6f05a-116">Miss lyckas om `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="6f05a-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f05a-117">Se även</span><span class="sxs-lookup"><span data-stu-id="6f05a-117">See Also</span></span>

- [<span data-ttu-id="6f05a-118">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="6f05a-118">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)