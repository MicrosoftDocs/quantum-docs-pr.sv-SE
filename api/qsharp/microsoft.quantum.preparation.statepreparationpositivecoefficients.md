---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: Funktionen StatePreparationPositiveCoefficients
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 081541d93bf853fa0de1573038dc00c296432281
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855848"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="165ab-102">Funktionen StatePreparationPositiveCoefficients</span><span class="sxs-lookup"><span data-stu-id="165ab-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="165ab-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="165ab-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="165ab-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="165ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="165ab-105">StatePreparationPositiveCoefficients är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="165ab-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="165ab-106">Använd <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> i stället.</span><span class="sxs-lookup"><span data-stu-id="165ab-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="165ab-107">Returnerar en åtgärd som förbereder angivet Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="165ab-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="165ab-108">Den returnerade åtgärden $U $ förbereder ett godtyckligt Quantum-tillstånd $ \ket{\psi} $ med positiva koefficienter $ \ alpha_j \ge $0 från $n $-qubit beräknings bas tillstånd $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="165ab-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="165ab-109">Åtgärden för U i ett nytilldelat register erhålls av $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="165ab-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="165ab-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="165ab-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="165ab-111">Indata</span><span class="sxs-lookup"><span data-stu-id="165ab-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="165ab-112">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="165ab-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="165ab-113">Matris med upp till $2 ^ n $ koefficienter $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="165ab-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="165ab-114">$J $ koefficienten indexerar Number State $ \ket{j} $ kodat i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="165ab-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="165ab-115">Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejusts + CTL</span><span class="sxs-lookup"><span data-stu-id="165ab-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="165ab-116">En enhetlig åtgärd för tillstånds förberedelse $U $.</span><span class="sxs-lookup"><span data-stu-id="165ab-116">A state-preparation unitary operation $U$.</span></span>

## <a name="example"></a><span data-ttu-id="165ab-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="165ab-117">Example</span></span>

<span data-ttu-id="165ab-118">Följande fragment förbereder Quantum-tillstånd $ \ket{\psi} = \ sqrt {1/8} \ ket {0} + \ sqrt {7/8} \ ket {2} $ i qubit-registreringen `qubitsLE` .</span><span class="sxs-lookup"><span data-stu-id="165ab-118">The following snippet prepares the quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{2}$ in the qubit register `qubitsLE`.</span></span>

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let op = StatePreparationPositiveCoefficients(amplitudes);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a><span data-ttu-id="165ab-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="165ab-119">Remarks</span></span>

<span data-ttu-id="165ab-120">Negativa ingångs-koefficienter $ \ alpha_j < $0 behandlas som om det är positivt med värdet $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="165ab-120">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="165ab-121">`coefficients` fylls i med elementen $ \ alpha_j = $0,0 om färre än $2 ^ n $ har angetts.</span><span class="sxs-lookup"><span data-stu-id="165ab-121">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>