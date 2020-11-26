---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: Funktionen StatePreparationComplexCoefficients
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 1d0efa7b83d2e8e75c4b293866f3929f357ec44b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210377"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="cbf04-102">Funktionen StatePreparationComplexCoefficients</span><span class="sxs-lookup"><span data-stu-id="cbf04-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="cbf04-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="cbf04-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="cbf04-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cbf04-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="cbf04-105">StatePreparationComplexCoefficients är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="cbf04-105">StatePreparationComplexCoefficients has been deprecated.</span></span> <span data-ttu-id="cbf04-106">Använd <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> i stället.</span><span class="sxs-lookup"><span data-stu-id="cbf04-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="cbf04-107">Returnerar en åtgärd som förbereder ett bestämt Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="cbf04-107">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="cbf04-108">Den returnerade åtgärden $U $ förbereder ett godtyckligt Quantum-tillstånd $ \ket{\psi} $ med komplexa koefficienter $r _j e ^ {i t_j} $ från $n $-qubit beräknings bas tillstånd $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="cbf04-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="cbf04-109">Åtgärden för U i ett nytilldelat register erhålls av $ $ \begin{align} U\ket {0... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="cbf04-109">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="cbf04-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="cbf04-110">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="cbf04-111">Indata</span><span class="sxs-lookup"><span data-stu-id="cbf04-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="cbf04-112">koefficienter: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="cbf04-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="cbf04-113">Matris med upp till $2 ^ n $ komplexa koefficienter som representeras av deras absoluta värde och fas $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="cbf04-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="cbf04-114">$J $ koefficienten indexerar Number State $ \ket{j} $ kodat i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="cbf04-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="cbf04-115">Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejusts + CTL</span><span class="sxs-lookup"><span data-stu-id="cbf04-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="cbf04-116">En enhetlig åtgärd för tillstånds förberedelse $U $.</span><span class="sxs-lookup"><span data-stu-id="cbf04-116">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="cbf04-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="cbf04-117">Remarks</span></span>

<span data-ttu-id="cbf04-118">Negativa ingångs-koefficienter $r _j < $0 behandlas som om det är positivt med värdet $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="cbf04-118">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="cbf04-119">`coefficients` fylls i med elementen $ (r_j, t_j) = (0,0, 0,0) $ om färre än $2 ^ n $ anges.</span><span class="sxs-lookup"><span data-stu-id="cbf04-119">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>