---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847612"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="dafb7-102">DrawRandomDouble-åtgärd</span><span class="sxs-lookup"><span data-stu-id="dafb7-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="dafb7-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="dafb7-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="dafb7-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dafb7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="dafb7-105">Ritar ett slumpmässigt reellt tal i ett angivet inklusiv-intervall.</span><span class="sxs-lookup"><span data-stu-id="dafb7-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="dafb7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="dafb7-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="dafb7-107">min: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dafb7-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dafb7-108">Det minsta reella tal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="dafb7-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="dafb7-109">Max: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dafb7-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dafb7-110">Det största reella tal som ska ritas.</span><span class="sxs-lookup"><span data-stu-id="dafb7-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="dafb7-111">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dafb7-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dafb7-112">Ett slumpmässigt reellt tal i inkluderar-intervallet från `min` till `max` med enhetlig sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="dafb7-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="dafb7-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="dafb7-113">Example</span></span>

<span data-ttu-id="dafb7-114">Följande Q #-kodfragment ritar slumpmässigt en vinkel mellan $0 $ och $2 \pi $:</span><span class="sxs-lookup"><span data-stu-id="dafb7-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a><span data-ttu-id="dafb7-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="dafb7-115">Remarks</span></span>

<span data-ttu-id="dafb7-116">Miss lyckas om `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="dafb7-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="dafb7-117">Se även</span><span class="sxs-lookup"><span data-stu-id="dafb7-117">See Also</span></span>

- [<span data-ttu-id="dafb7-118">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="dafb7-118">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)