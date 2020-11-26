---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192952"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="98c35-102">DrawRandomDouble-åtgärd</span><span class="sxs-lookup"><span data-stu-id="98c35-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="98c35-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="98c35-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="98c35-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="98c35-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="98c35-105">Ritar ett slumpmässigt reellt tal i ett angivet inklusiv-intervall.</span><span class="sxs-lookup"><span data-stu-id="98c35-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="98c35-106">Indata</span><span class="sxs-lookup"><span data-stu-id="98c35-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="98c35-107">min: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="98c35-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="98c35-108">Det minsta reella tal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="98c35-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="98c35-109">Max: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="98c35-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="98c35-110">Det största reella tal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="98c35-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="98c35-111">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="98c35-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="98c35-112">Ett slumpmässigt reellt tal i inkluderar-intervallet från `min` till `max` med enhetlig sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="98c35-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="98c35-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="98c35-113">Remarks</span></span>

<span data-ttu-id="98c35-114">Miss lyckas om `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="98c35-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="98c35-115">Se även</span><span class="sxs-lookup"><span data-stu-id="98c35-115">See Also</span></span>

- [<span data-ttu-id="98c35-116">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="98c35-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)