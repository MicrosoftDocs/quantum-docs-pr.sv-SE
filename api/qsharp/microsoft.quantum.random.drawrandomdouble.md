---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733211"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="14eb1-102">DrawRandomDouble-åtgärd</span><span class="sxs-lookup"><span data-stu-id="14eb1-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="14eb1-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="14eb1-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="14eb1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="14eb1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="14eb1-105">Ritar ett slumpmässigt reellt tal i ett angivet inklusiv-intervall.</span><span class="sxs-lookup"><span data-stu-id="14eb1-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="14eb1-106">Indata</span><span class="sxs-lookup"><span data-stu-id="14eb1-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="14eb1-107">min: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="14eb1-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="14eb1-108">Det minsta reella tal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="14eb1-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="14eb1-109">Max: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="14eb1-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="14eb1-110">Det största reella tal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="14eb1-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="14eb1-111">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="14eb1-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="14eb1-112">Ett slumpmässigt reellt tal i inkluderar-intervallet från `min` till `max` med enhetlig sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="14eb1-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="14eb1-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="14eb1-113">Remarks</span></span>

<span data-ttu-id="14eb1-114">Miss lyckas om `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="14eb1-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="14eb1-115">Se även</span><span class="sxs-lookup"><span data-stu-id="14eb1-115">See Also</span></span>

- [<span data-ttu-id="14eb1-116">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="14eb1-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)