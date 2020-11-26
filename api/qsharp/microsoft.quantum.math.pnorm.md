---
uid: Microsoft.Quantum.Math.PNorm
title: Funktionen PNorm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194737"
---
# <a name="pnorm-function"></a><span data-ttu-id="9c9f5-102">Funktionen PNorm</span><span class="sxs-lookup"><span data-stu-id="9c9f5-102">PNorm function</span></span>

<span data-ttu-id="9c9f5-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9c9f5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9c9f5-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9c9f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9c9f5-105">Returnerar `L(p)` normen för en Vector of `Double` s.</span><span class="sxs-lookup"><span data-stu-id="9c9f5-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="9c9f5-106">Det vill säga att en matris $x $ av typ `Double[]` returnerar detta $p $-norm $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $.</span><span class="sxs-lookup"><span data-stu-id="9c9f5-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="9c9f5-107">Indata</span><span class="sxs-lookup"><span data-stu-id="9c9f5-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="9c9f5-108">p: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9c9f5-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9c9f5-109">Exponenten $p $ i $p $-norm.</span><span class="sxs-lookup"><span data-stu-id="9c9f5-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="9c9f5-110">matris: [dubbel](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9c9f5-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="9c9f5-111">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9c9f5-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9c9f5-112">$P $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="9c9f5-112">The $p$-norm $\|x\|_p$.</span></span>