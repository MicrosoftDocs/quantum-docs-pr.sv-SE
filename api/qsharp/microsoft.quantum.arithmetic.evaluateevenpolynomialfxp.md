---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: c3129cb796a344f7ad38a585183db285d48892bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843238"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="58c14-102">EvaluateEvenPolynomialFxP-åtgärd</span><span class="sxs-lookup"><span data-stu-id="58c14-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="58c14-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="58c14-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="58c14-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="58c14-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="58c14-105">Utvärderar en jämn polynom i en fast punkts representation.</span><span class="sxs-lookup"><span data-stu-id="58c14-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="58c14-106">Indata</span><span class="sxs-lookup"><span data-stu-id="58c14-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="58c14-107">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="58c14-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="58c14-108">Koefficienter för jämnt polynomed som en dubbel matris, d.v.s. matrisen $ [a_0, a_1,..., a_k] $ för den jämnt polynom $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2} $.</span><span class="sxs-lookup"><span data-stu-id="58c14-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="58c14-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="58c14-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="58c14-110">Inmatat punkt nummer för vilket polynomen ska utvärderas.</span><span class="sxs-lookup"><span data-stu-id="58c14-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="58c14-111">resultat: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="58c14-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="58c14-112">Anger ett fast punkt-värde för utdata som innehåller $P (x) $.</span><span class="sxs-lookup"><span data-stu-id="58c14-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="58c14-113">Måste vara i tillstånd $ \ket {0} $ initialt.</span><span class="sxs-lookup"><span data-stu-id="58c14-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="58c14-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="58c14-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

