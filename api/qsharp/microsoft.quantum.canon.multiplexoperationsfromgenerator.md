---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: MultiplexOperationsFromGenerator-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2fde0bf391568f39128e6dca4b535aa6b78407c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728542"
---
# <a name="multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="7ad26-102">MultiplexOperationsFromGenerator-åtgärd</span><span class="sxs-lookup"><span data-stu-id="7ad26-102">MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="7ad26-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7ad26-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7ad26-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7ad26-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7ad26-105">Använder en multiplicering-kontrollerad enhetlig åtgärd $U $ som tillämpar en enhetlig $V _j $ när den styrs av n-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="7ad26-105">Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="7ad26-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="7ad26-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="7ad26-107">Indata</span><span class="sxs-lookup"><span data-stu-id="7ad26-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a><span data-ttu-id="7ad26-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> t => [Unit](xref:microsoft.quantum.lang-ref.unit) rejust + CTL)</span><span class="sxs-lookup"><span data-stu-id="7ad26-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="7ad26-109">En tupel där det första elementet `Int` är antalet unitaries $N $, och det andra elementet `(Int -> ('T => () is Adj + Ctl))` är en funktion som tar ett heltal $j $ i $ [0, N-1] $ och utvärderar den enhetliga åtgärden $V _J $.</span><span class="sxs-lookup"><span data-stu-id="7ad26-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="7ad26-110">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7ad26-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7ad26-111">$n $-qubit Control register som kodar nummer tillstånden $ \ket{j} $ i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="7ad26-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="7ad26-112">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="7ad26-112">target : 'T</span></span>

<span data-ttu-id="7ad26-113">Allmän qubit-registrering som $V _j $ agerar på.</span><span class="sxs-lookup"><span data-stu-id="7ad26-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7ad26-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7ad26-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7ad26-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="7ad26-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7ad26-116">Inte</span><span class="sxs-lookup"><span data-stu-id="7ad26-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="7ad26-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="7ad26-117">Remarks</span></span>

<span data-ttu-id="7ad26-118">`coefficients` fylls i med identitets element om färre än $2 ^ n $ anges.</span><span class="sxs-lookup"><span data-stu-id="7ad26-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="7ad26-119">Den här implementeringen använder $n-$1-hjälp qubits.</span><span class="sxs-lookup"><span data-stu-id="7ad26-119">This implementation uses $n-1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="7ad26-120">Referenser</span><span class="sxs-lookup"><span data-stu-id="7ad26-120">References</span></span>

- [<span data-ttu-id="7ad26-121">*Andrew M. Children, Dmitri Maslov, Yunseong, Neil J. värskogsnätverksväxling, Yuan Su* , arXiv: 1711.10980</span><span class="sxs-lookup"><span data-stu-id="7ad26-121"> *Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su* , arXiv:1711.10980</span></span>](https://arxiv.org/abs/1711.10980)