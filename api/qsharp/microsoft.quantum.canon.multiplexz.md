---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: MultiplexZ-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: dccfe86104263e23794bce33279e8748f11f5a54
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852429"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="a092e-102">MultiplexZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a092e-102">MultiplexZ operation</span></span>

<span data-ttu-id="a092e-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a092e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a092e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a092e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a092e-105">Använder en Pauli Z-rotation i en matris med qubits.</span><span class="sxs-lookup"><span data-stu-id="a092e-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a092e-106">Description</span><span class="sxs-lookup"><span data-stu-id="a092e-106">Description</span></span>

<span data-ttu-id="a092e-107">Detta använder den multiplicerade, konsekventa åtgärden som utför rotationer efter vinkeln $ \ theta_j $ om Single-qubit Pauli-operatorn $Z $ när den styrs av $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="a092e-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="a092e-108">Den här åtgärden kan särskilt representeras av den enhetliga</span><span class="sxs-lookup"><span data-stu-id="a092e-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="a092e-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="a092e-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="a092e-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a092e-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="a092e-111">Indata</span><span class="sxs-lookup"><span data-stu-id="a092e-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="a092e-112">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a092e-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a092e-113">Matris med upp till $2 ^ n $ koefficienter $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="a092e-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="a092e-114">$J $ koefficienten indexerar Number State $ \ket{j} $ kodat i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="a092e-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="a092e-115">kontroll: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a092e-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a092e-116">$n $-qubit Control register som kodar nummer tillstånden $ \ket{j} $ i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="a092e-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a092e-117">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a092e-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a092e-118">Enda qubit-register som roteras av $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="a092e-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a092e-119">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a092e-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a092e-120">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a092e-120">Remarks</span></span>

<span data-ttu-id="a092e-121">`coefficients` fylls i med elementen $ \ theta_j = $0,0 om färre än $2 ^ n $ har angetts.</span><span class="sxs-lookup"><span data-stu-id="a092e-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="a092e-122">Referenser</span><span class="sxs-lookup"><span data-stu-id="a092e-122">References</span></span>

- <span data-ttu-id="a092e-123">Syntes av Quantum Logic-kretsar Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="a092e-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="a092e-124">Se även</span><span class="sxs-lookup"><span data-stu-id="a092e-124">See Also</span></span>

- [<span data-ttu-id="a092e-125">Microsoft. Quantum. Canon. ApproximatelyMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="a092e-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)