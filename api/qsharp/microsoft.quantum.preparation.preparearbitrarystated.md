---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateD
title: PrepareArbitraryStateD-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: cca0ea16dca3f3da8ce76a43f1012ffa0e4a72e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210615"
---
# <a name="preparearbitrarystated-operation"></a><span data-ttu-id="88bd8-102">PrepareArbitraryStateD-åtgärd</span><span class="sxs-lookup"><span data-stu-id="88bd8-102">PrepareArbitraryStateD operation</span></span>

<span data-ttu-id="88bd8-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="88bd8-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="88bd8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88bd8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88bd8-105">Med hänsyn till en uppsättning koefficienter och ett litet endian-kodat Quantum-register, förbereder ett tillstånd i detta register som beskrivs av de angivna koefficienterna.</span><span class="sxs-lookup"><span data-stu-id="88bd8-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryStateD (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="88bd8-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="88bd8-106">Description</span></span>

<span data-ttu-id="88bd8-107">Den här åtgärden förbereder ett godtyckligt Quantum-tillstånd $ \ket{\psi} $ med komplexa koefficienter $r _j e ^ {i t_j} $ från $n $-qubit beräknings bas tillstånd $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="88bd8-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="88bd8-108">I synnerhet kan åtgärden för den här åtgärden simuleras av en enhetlig omvandling $U $ som agerar på status all – noll som</span><span class="sxs-lookup"><span data-stu-id="88bd8-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ that acts on the all-zeros state as</span></span>

<span data-ttu-id="88bd8-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="88bd8-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="88bd8-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="88bd8-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="88bd8-111">Indata</span><span class="sxs-lookup"><span data-stu-id="88bd8-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="88bd8-112">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="88bd8-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="88bd8-113">Matris med upp till $2 ^ n $ Real-koefficienter.</span><span class="sxs-lookup"><span data-stu-id="88bd8-113">Array of up to $2^n$ real coefficients.</span></span> <span data-ttu-id="88bd8-114">$J $ koefficienten indexerar Number State $ \ket{j} $ kodat i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="88bd8-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="88bd8-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="88bd8-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="88bd8-116">Qubit registrerar kodnings nummer tillstånd i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="88bd8-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="88bd8-117">Detta förväntas bli initierat i beräknings grund tillstånd $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="88bd8-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="88bd8-118">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="88bd8-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="88bd8-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="88bd8-119">Remarks</span></span>

<span data-ttu-id="88bd8-120">Negativa ingångs-koefficienter $r _j < $0 behandlas som om det är positivt med värdet $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="88bd8-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="88bd8-121">`coefficients` fylls i med elementen $ (r_j, t_j) = (0,0, 0,0) $ om färre än $2 ^ n $ anges.</span><span class="sxs-lookup"><span data-stu-id="88bd8-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="88bd8-122">Referenser</span><span class="sxs-lookup"><span data-stu-id="88bd8-122">References</span></span>

- <span data-ttu-id="88bd8-123">Syntes av Quantum Logic-kretsar Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="88bd8-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="88bd8-124">Se även</span><span class="sxs-lookup"><span data-stu-id="88bd8-124">See Also</span></span>

- [<span data-ttu-id="88bd8-125">Microsoft. Quantum. preparation. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="88bd8-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)