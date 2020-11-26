---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: MultiplexOperationsBruteForceFromGenerator-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: a700cffbd8fe8be01fdb7344cc9d4b02a4900174
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206008"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a><span data-ttu-id="ab3e6-102">MultiplexOperationsBruteForceFromGenerator-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ab3e6-102">MultiplexOperationsBruteForceFromGenerator operation</span></span>

<span data-ttu-id="ab3e6-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ab3e6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ab3e6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab3e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab3e6-105">Tillämpar en multiplicering-kontrollerad enhetlig åtgärd $U $ som tillämpar en enhetlig $V _j $ när det styrs av n-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="ab3e6-105">Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="ab3e6-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="ab3e6-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ab3e6-107">Indata</span><span class="sxs-lookup"><span data-stu-id="ab3e6-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="ab3e6-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är just + CTL)</span><span class="sxs-lookup"><span data-stu-id="ab3e6-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="ab3e6-109">En tupel där det första elementet `Int` är antalet unitaries $N $, och det andra elementet `(Int -> ('T => () is Adj + Ctl))` är en funktion som tar ett heltal $j $ i $ [0, N-1] $ och utvärderar den enhetliga åtgärden $V _J $.</span><span class="sxs-lookup"><span data-stu-id="ab3e6-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="ab3e6-110">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ab3e6-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ab3e6-111">$n $-qubit Control register som kodar nummer tillstånden $ \ket{j} $ i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="ab3e6-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="ab3e6-112">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="ab3e6-112">target : 'T</span></span>

<span data-ttu-id="ab3e6-113">Allmän qubit-registrering som $V _j $ agerar på.</span><span class="sxs-lookup"><span data-stu-id="ab3e6-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ab3e6-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab3e6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ab3e6-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ab3e6-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ab3e6-116">Inte</span><span class="sxs-lookup"><span data-stu-id="ab3e6-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="ab3e6-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ab3e6-117">Remarks</span></span>

<span data-ttu-id="ab3e6-118">`coefficients` fylls i med identitets element om färre än $2 ^ n $ anges.</span><span class="sxs-lookup"><span data-stu-id="ab3e6-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="ab3e6-119">Den här versionen implementeras direkt genom slingor via n-styrda enhetliga operatörer.</span><span class="sxs-lookup"><span data-stu-id="ab3e6-119">This version is implemented directly by looping through n-controlled unitary operators.</span></span>