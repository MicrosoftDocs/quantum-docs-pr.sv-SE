---
uid: Microsoft.Quantum.Canon.MultiplexPauli
title: MultiplexPauli-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits.
ms.openlocfilehash: 0714e796c1e5ad097814bcf507f49f59a844e9ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728536"
---
# <a name="multiplexpauli-operation"></a><span data-ttu-id="635d6-102">MultiplexPauli-åtgärd</span><span class="sxs-lookup"><span data-stu-id="635d6-102">MultiplexPauli operation</span></span>

<span data-ttu-id="635d6-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="635d6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="635d6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="635d6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="635d6-105">Använder en Pauli-rotation som är villkorlig på en matris med qubits.</span><span class="sxs-lookup"><span data-stu-id="635d6-105">Applies a Pauli rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexPauli (coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="635d6-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="635d6-106">Description</span></span>

<span data-ttu-id="635d6-107">Detta använder en multiplicering-kontrollerad enhetlig åtgärd som utför rotationer efter vinkeln $ \ theta_j $ om Single-qubit Pauli-operatorn $P $ när den styrs av $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="635d6-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="635d6-108">I synnerhet representeras åtgärden för den här åtgärden av den enhetliga</span><span class="sxs-lookup"><span data-stu-id="635d6-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="635d6-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="635d6-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="635d6-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="635d6-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="635d6-111">Indata</span><span class="sxs-lookup"><span data-stu-id="635d6-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="635d6-112">koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="635d6-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="635d6-113">Matris med upp till $2 ^ n $ koefficienter $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="635d6-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="635d6-114">$J $ koefficienten indexerar Number State $ \ket{j} $ kodat i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="635d6-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="635d6-115">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="635d6-115">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="635d6-116">Pauli-operator $P $ som bestämmer rotations axeln.</span><span class="sxs-lookup"><span data-stu-id="635d6-116">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="635d6-117">kontroll: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="635d6-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="635d6-118">$n $-qubit Control register som kodar nummer tillstånden $ \ket{j} $ i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="635d6-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="635d6-119">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="635d6-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="635d6-120">Enda qubit-register som roteras av $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="635d6-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="635d6-121">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="635d6-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="635d6-122">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="635d6-122">Remarks</span></span>

<span data-ttu-id="635d6-123">`coefficients` fylls i med elementen $ \ theta_j = $0,0 om färre än $2 ^ n $ har angetts.</span><span class="sxs-lookup"><span data-stu-id="635d6-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="635d6-124">Se även</span><span class="sxs-lookup"><span data-stu-id="635d6-124">See Also</span></span>

- [<span data-ttu-id="635d6-125">Microsoft. Quantum. Canon. ApproximatelyMultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="635d6-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli)