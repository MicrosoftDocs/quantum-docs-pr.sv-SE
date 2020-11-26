---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: Funktionen ContinuousUniformDistribution
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193088"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="81811-102">Funktionen ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="81811-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="81811-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="81811-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="81811-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="81811-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="81811-105">Returnerar en enhetlig distribution över ett angivet inklusiv-intervall.</span><span class="sxs-lookup"><span data-stu-id="81811-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="81811-106">Indata</span><span class="sxs-lookup"><span data-stu-id="81811-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="81811-107">min: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81811-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="81811-108">Det minsta reella tal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="81811-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="81811-109">Max: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81811-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="81811-110">Det största reella tal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="81811-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="81811-111">Utdata: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="81811-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="81811-112">En distribution vars slumpmässiga variates är reella tal i inklusiv-intervallet från `min` till `max` med enhetlig sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="81811-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="81811-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="81811-113">Remarks</span></span>

<span data-ttu-id="81811-114">Miss lyckas om `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="81811-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="81811-115">Se även</span><span class="sxs-lookup"><span data-stu-id="81811-115">See Also</span></span>

- [<span data-ttu-id="81811-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="81811-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)