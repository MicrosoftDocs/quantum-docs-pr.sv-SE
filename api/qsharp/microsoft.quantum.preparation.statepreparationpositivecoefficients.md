---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: Funktionen StatePreparationPositiveCoefficients
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732587"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="e83dc-102">Funktionen StatePreparationPositiveCoefficients</span><span class="sxs-lookup"><span data-stu-id="e83dc-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="e83dc-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e83dc-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e83dc-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e83dc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e83dc-105">Returnerar en åtgärd som förbereder angivet Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="e83dc-105">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="e83dc-106">Den returnerade åtgärden $U $ förbereder ett godtyckligt Quantum-tillstånd $ \ket{\psi} $ med positiva koefficienter $ \ alpha_j \ge $0 från $n $-qubit beräknings bas tillstånd $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="e83dc-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="e83dc-107">Åtgärden för U i ett nytilldelat register erhålls av $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="e83dc-107">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="e83dc-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="e83dc-108">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="e83dc-109">Indata</span><span class="sxs-lookup"><span data-stu-id="e83dc-109">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="e83dc-110">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e83dc-110">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e83dc-111">Matris med upp till $2 ^ n $ koefficienter $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="e83dc-111">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="e83dc-112">$J $ koefficienten indexerar Number State $ \ket{j} $ kodat i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="e83dc-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="e83dc-113">Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="e83dc-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="e83dc-114">En enhetlig åtgärd för tillstånds förberedelse $U $.</span><span class="sxs-lookup"><span data-stu-id="e83dc-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="e83dc-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="e83dc-115">Remarks</span></span>

<span data-ttu-id="e83dc-116">Negativa ingångs-koefficienter $ \ alpha_j < $0 behandlas som om det är positivt med värdet $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="e83dc-116">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="e83dc-117">`coefficients` fylls i med elementen $ \ alpha_j = $0,0 om färre än $2 ^ n $ har angetts.</span><span class="sxs-lookup"><span data-stu-id="e83dc-117">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>