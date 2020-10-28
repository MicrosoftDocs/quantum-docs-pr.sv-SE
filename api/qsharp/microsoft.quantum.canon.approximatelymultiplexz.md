---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: ApproximatelyMultiplexZ-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: ac5195b8b3afaad4d41fe50d45652644e2397e1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728968"
---
# <a name="approximatelymultiplexz-operation"></a><span data-ttu-id="335c6-102">ApproximatelyMultiplexZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="335c6-102">ApproximatelyMultiplexZ operation</span></span>

<span data-ttu-id="335c6-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="335c6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="335c6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="335c6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="335c6-105">Använder en Pauli Z-rotation i en matris med qubits, trunkerar små rotations vinklar enligt en viss tolerans.</span><span class="sxs-lookup"><span data-stu-id="335c6-105">Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="335c6-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="335c6-106">Description</span></span>

<span data-ttu-id="335c6-107">Detta använder den multiplicerade, konsekventa åtgärden som utför rotationer efter vinkeln $ \ theta_j $ om Single-qubit Pauli-operatorn $Z $ när den styrs av $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="335c6-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="335c6-108">Den här åtgärden kan särskilt representeras av den enhetliga</span><span class="sxs-lookup"><span data-stu-id="335c6-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="335c6-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="335c6-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="335c6-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="335c6-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="335c6-111">Indata</span><span class="sxs-lookup"><span data-stu-id="335c6-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="335c6-112">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="335c6-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="335c6-113">En tolerans under vilken små koefficienter trunkeras.</span><span class="sxs-lookup"><span data-stu-id="335c6-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="335c6-114">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="335c6-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="335c6-115">Matris med upp till $2 ^ n $ koefficienter $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="335c6-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="335c6-116">$J $ koefficienten indexerar Number State $ \ket{j} $ kodat i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="335c6-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="335c6-117">kontroll: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="335c6-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="335c6-118">$n $-qubit Control register som kodar nummer tillstånden $ \ket{j} $ i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="335c6-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="335c6-119">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="335c6-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="335c6-120">Enda qubit-register som roteras av $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="335c6-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="335c6-121">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="335c6-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="335c6-122">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="335c6-122">Remarks</span></span>

<span data-ttu-id="335c6-123">`coefficients` fylls i med elementen $ \ theta_j = $0,0 om färre än $2 ^ n $ har angetts.</span><span class="sxs-lookup"><span data-stu-id="335c6-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="335c6-124">Referenser</span><span class="sxs-lookup"><span data-stu-id="335c6-124">References</span></span>

- <span data-ttu-id="335c6-125">Syntes av Quantum Logic-kretsar Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="335c6-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="335c6-126">Se även</span><span class="sxs-lookup"><span data-stu-id="335c6-126">See Also</span></span>

- [<span data-ttu-id="335c6-127">Microsoft. Quantum. Canon. MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="335c6-127">Microsoft.Quantum.Canon.MultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.MultiplexZ)