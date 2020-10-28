---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: MultiplexZ-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: f7b1973e18ad396ebe892ad63ae47374a7cafbd5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728533"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="aa53c-102">MultiplexZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="aa53c-102">MultiplexZ operation</span></span>

<span data-ttu-id="aa53c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa53c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa53c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa53c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa53c-105">Använder en Pauli Z-rotation i en matris med qubits.</span><span class="sxs-lookup"><span data-stu-id="aa53c-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="aa53c-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="aa53c-106">Description</span></span>

<span data-ttu-id="aa53c-107">Detta använder den multiplicerade, konsekventa åtgärden som utför rotationer efter vinkeln $ \ theta_j $ om Single-qubit Pauli-operatorn $Z $ när den styrs av $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="aa53c-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="aa53c-108">Den här åtgärden kan särskilt representeras av den enhetliga</span><span class="sxs-lookup"><span data-stu-id="aa53c-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="aa53c-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="aa53c-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="aa53c-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="aa53c-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="aa53c-111">Indata</span><span class="sxs-lookup"><span data-stu-id="aa53c-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="aa53c-112">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="aa53c-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="aa53c-113">Matris med upp till $2 ^ n $ koefficienter $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="aa53c-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="aa53c-114">$J $ koefficienten indexerar Number State $ \ket{j} $ kodat i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="aa53c-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="aa53c-115">kontroll: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="aa53c-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aa53c-116">$n $-qubit Control register som kodar nummer tillstånden $ \ket{j} $ i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="aa53c-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="aa53c-117">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aa53c-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aa53c-118">Enda qubit-register som roteras av $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="aa53c-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa53c-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa53c-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aa53c-120">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="aa53c-120">Remarks</span></span>

<span data-ttu-id="aa53c-121">`coefficients` fylls i med elementen $ \ theta_j = $0,0 om färre än $2 ^ n $ har angetts.</span><span class="sxs-lookup"><span data-stu-id="aa53c-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="aa53c-122">Referenser</span><span class="sxs-lookup"><span data-stu-id="aa53c-122">References</span></span>

- <span data-ttu-id="aa53c-123">Syntes av Quantum Logic-kretsar Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="aa53c-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="aa53c-124">Se även</span><span class="sxs-lookup"><span data-stu-id="aa53c-124">See Also</span></span>

- [<span data-ttu-id="aa53c-125">Microsoft. Quantum. Canon. ApproximatelyMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="aa53c-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)