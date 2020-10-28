---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: ApproximatelyApplyDiagonalUnitary-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 9d9b1ced320b142aef2a2cd8f3335f855d37048f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728980"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a><span data-ttu-id="eacec-102">ApproximatelyApplyDiagonalUnitary-åtgärd</span><span class="sxs-lookup"><span data-stu-id="eacec-102">ApproximatelyApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="eacec-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eacec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eacec-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eacec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eacec-105">Använder en matris med komplexa faser till numeriska bas tillstånd för ett register över qubits, vilket trunkerar små rotations vinklar enligt en viss tolerans.</span><span class="sxs-lookup"><span data-stu-id="eacec-105">Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="eacec-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="eacec-106">Description</span></span>

<span data-ttu-id="eacec-107">Den här åtgärden implementerar en diagonalt som använder en komplex fas $e ^ {i \ theta_j} $ på $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="eacec-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="eacec-108">Den här åtgärden kan särskilt representeras av den enhetliga</span><span class="sxs-lookup"><span data-stu-id="eacec-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="eacec-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="eacec-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="eacec-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="eacec-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="eacec-111">Indata</span><span class="sxs-lookup"><span data-stu-id="eacec-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="eacec-112">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eacec-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eacec-113">En tolerans under vilken små koefficienter trunkeras.</span><span class="sxs-lookup"><span data-stu-id="eacec-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="eacec-114">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="eacec-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="eacec-115">Matris med upp till $2 ^ n $ koefficienter $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="eacec-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="eacec-116">$J $ koefficienten indexerar Number State $ \ket{j} $ kodat i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="eacec-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="eacec-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="eacec-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="eacec-118">$n $-qubit Control register som kodar nummer tillstånden $ \ket{j} $ i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="eacec-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eacec-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eacec-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="eacec-120">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="eacec-120">Remarks</span></span>

<span data-ttu-id="eacec-121">`coefficients` fylls i med elementen $ \ theta_j = $0,0 om färre än $2 ^ n $ har angetts.</span><span class="sxs-lookup"><span data-stu-id="eacec-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="eacec-122">Referenser</span><span class="sxs-lookup"><span data-stu-id="eacec-122">References</span></span>

- <span data-ttu-id="eacec-123">Syntes av Quantum Logic-kretsar Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="eacec-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="eacec-124">Se även</span><span class="sxs-lookup"><span data-stu-id="eacec-124">See Also</span></span>

- [<span data-ttu-id="eacec-125">Microsoft. Quantum. Canon. ApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="eacec-125">Microsoft.Quantum.Canon.ApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)