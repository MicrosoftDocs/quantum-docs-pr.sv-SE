---
uid: Microsoft.Quantum.Math.PNormalized
title: Funktionen PNormalized
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732238"
---
# <a name="pnormalized-function"></a><span data-ttu-id="874bd-102">Funktionen PNormalized</span><span class="sxs-lookup"><span data-stu-id="874bd-102">PNormalized function</span></span>

<span data-ttu-id="874bd-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="874bd-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="874bd-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="874bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="874bd-105">Normaliserar en Vector of `Double` s i `L(p)` normen.</span><span class="sxs-lookup"><span data-stu-id="874bd-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="874bd-106">Det vill säga, med en matris $x $ av typen `Double[]` , returnerar detta en matris där alla element delas av $p $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="874bd-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="874bd-107">Indata</span><span class="sxs-lookup"><span data-stu-id="874bd-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="874bd-108">p: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="874bd-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="874bd-109">Exponenten $p $ i $p $-norm.</span><span class="sxs-lookup"><span data-stu-id="874bd-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="874bd-110">matris: [dubbel](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="874bd-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="874bd-111">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="874bd-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="874bd-112">Matrisen $x $ normaliseras av $p $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="874bd-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="874bd-113">Se även</span><span class="sxs-lookup"><span data-stu-id="874bd-113">See Also</span></span>

- [<span data-ttu-id="874bd-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="874bd-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)