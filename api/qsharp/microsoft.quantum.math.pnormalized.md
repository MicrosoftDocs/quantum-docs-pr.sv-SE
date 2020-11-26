---
uid: Microsoft.Quantum.Math.PNormalized
title: Funktionen PNormalized
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 196bdab67528aa8672a010ac3830459e27276ce9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227530"
---
# <a name="pnormalized-function"></a><span data-ttu-id="5f087-102">Funktionen PNormalized</span><span class="sxs-lookup"><span data-stu-id="5f087-102">PNormalized function</span></span>

<span data-ttu-id="5f087-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5f087-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5f087-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5f087-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5f087-105">Normaliserar en Vector of `Double` s i `L(p)` normen.</span><span class="sxs-lookup"><span data-stu-id="5f087-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="5f087-106">Det vill säga, med en matris $x $ av typen `Double[]` , returnerar detta en matris där alla element delas av $p $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="5f087-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="5f087-107">Indata</span><span class="sxs-lookup"><span data-stu-id="5f087-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="5f087-108">p: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5f087-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5f087-109">Exponenten $p $ i $p $-norm.</span><span class="sxs-lookup"><span data-stu-id="5f087-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="5f087-110">matris: [dubbel](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5f087-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="5f087-111">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5f087-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="5f087-112">Matrisen $x $ normaliseras av $p $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="5f087-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f087-113">Se även</span><span class="sxs-lookup"><span data-stu-id="5f087-113">See Also</span></span>

- [<span data-ttu-id="5f087-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="5f087-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)