---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 1bf9b6e7c416e994e70b93e5967caefd444f6426
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223229"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="79c7a-102">EvaluateOddPolynomialFxP-åtgärd</span><span class="sxs-lookup"><span data-stu-id="79c7a-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="79c7a-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="79c7a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="79c7a-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="79c7a-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="79c7a-105">Utvärderar en udda polynom i en fast punkts representation.</span><span class="sxs-lookup"><span data-stu-id="79c7a-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="79c7a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="79c7a-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="79c7a-107">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="79c7a-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="79c7a-108">Koefficienter för den udda polynomen som en dubbel matris, d.v.s. matrisen $ [a_0, a_1,..., a_k] $ för den udda polynom $P (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2 000 + 1} $.</span><span class="sxs-lookup"><span data-stu-id="79c7a-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="79c7a-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="79c7a-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="79c7a-110">Inmatat punkt nummer för vilket polynomen ska utvärderas.</span><span class="sxs-lookup"><span data-stu-id="79c7a-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="79c7a-111">resultat: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="79c7a-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="79c7a-112">Utgående punkt värde för utdata som innehåller P (x).</span><span class="sxs-lookup"><span data-stu-id="79c7a-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="79c7a-113">Måste vara i tillstånd $ \ket {0} $ initialt.</span><span class="sxs-lookup"><span data-stu-id="79c7a-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="79c7a-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="79c7a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

