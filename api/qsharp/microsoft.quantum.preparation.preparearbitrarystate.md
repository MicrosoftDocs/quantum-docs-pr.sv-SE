---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: PrepareArbitraryState-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > PrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 18a1e86f8e110a8f48d7dd50961e1f1f471ffc4e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190708"
---
# <a name="preparearbitrarystate-operation"></a><span data-ttu-id="e1d67-102">PrepareArbitraryState-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e1d67-102">PrepareArbitraryState operation</span></span>

<span data-ttu-id="e1d67-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e1d67-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e1d67-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1d67-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="e1d67-105">PrepareArbitraryState är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="e1d67-105">PrepareArbitraryState has been deprecated.</span></span> <span data-ttu-id="e1d67-106">Använd <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> i stället.</span><span class="sxs-lookup"><span data-stu-id="e1d67-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="e1d67-107">Med hänsyn till en uppsättning koefficienter och ett litet endian-kodat Quantum-register, förbereder ett tillstånd i detta register som beskrivs av de angivna koefficienterna.</span><span class="sxs-lookup"><span data-stu-id="e1d67-107">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e1d67-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e1d67-108">Description</span></span>

<span data-ttu-id="e1d67-109">Den här åtgärden förbereder ett godtyckligt Quantum-tillstånd $ \ket{\psi} $ med komplexa koefficienter $r _j e ^ {i t_j} $ från $n $-qubit beräknings bas tillstånd $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="e1d67-109">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="e1d67-110">I synnerhet kan åtgärden för den här åtgärden simuleras av en enhetlig omvandling $U $ som fungerar med status all – noll som</span><span class="sxs-lookup"><span data-stu-id="e1d67-110">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="e1d67-111">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="e1d67-111">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="e1d67-112">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="e1d67-112">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="e1d67-113">Indata</span><span class="sxs-lookup"><span data-stu-id="e1d67-113">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="e1d67-114">koefficienter: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="e1d67-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="e1d67-115">Matris med upp till $2 ^ n $ komplexa koefficienter som representeras av deras absoluta värde och fas $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="e1d67-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="e1d67-116">$J $ koefficienten indexerar Number State $ \ket{j} $ kodat i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="e1d67-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="e1d67-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e1d67-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e1d67-118">Qubit registrerar kodnings nummer tillstånd i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="e1d67-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="e1d67-119">Detta förväntas bli initierat i beräknings grund tillstånd $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="e1d67-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1d67-120">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1d67-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e1d67-121">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="e1d67-121">Remarks</span></span>

<span data-ttu-id="e1d67-122">Negativa ingångs-koefficienter $r _j < $0 behandlas som om det är positivt med värdet $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="e1d67-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="e1d67-123">`coefficients` fylls i med elementen $ (r_j, t_j) = (0,0, 0,0) $ om färre än $2 ^ n $ anges.</span><span class="sxs-lookup"><span data-stu-id="e1d67-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="e1d67-124">Referenser</span><span class="sxs-lookup"><span data-stu-id="e1d67-124">References</span></span>

- <span data-ttu-id="e1d67-125">Syntes av Quantum Logic-kretsar Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="e1d67-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="e1d67-126">Se även</span><span class="sxs-lookup"><span data-stu-id="e1d67-126">See Also</span></span>

- [<span data-ttu-id="e1d67-127">Microsoft. Quantum. preparation. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="e1d67-127">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)