---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: f33d2980ff1775b1ae8d2e2e7a4fa1e5cbe7d5ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858867"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="f4c34-102">ApplyPermutationUsingDecompositionWithVariableOrder-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f4c34-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="f4c34-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f4c34-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f4c34-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4c34-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4c34-105">Permutes amplituderna i ett Quantum-tillstånd med en permutation med hjälp av nedbrytnings syntes.</span><span class="sxs-lookup"><span data-stu-id="f4c34-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f4c34-106">Description</span><span class="sxs-lookup"><span data-stu-id="f4c34-106">Description</span></span>

<span data-ttu-id="f4c34-107">Den här åtgärden är en mer allmän version av @"microsoft.quantum.synthesis.applypermutationusingdecomposition" där variabeln kan anges.</span><span class="sxs-lookup"><span data-stu-id="f4c34-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="f4c34-108">En annan variabel ordning ändrar insammansättnings ordningen och de sanningen-tabeller som används för de kontrollerade @"microsoft.quantum.intrinsic.x" grindarna.</span><span class="sxs-lookup"><span data-stu-id="f4c34-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="f4c34-109">Därför ändrar variabel ordningen antalet allmänna grindar som används för att realisera permutationen.</span><span class="sxs-lookup"><span data-stu-id="f4c34-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="f4c34-110">Indata</span><span class="sxs-lookup"><span data-stu-id="f4c34-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="f4c34-111">behörighet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f4c34-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f4c34-112">En permutation av $2 ^ n $ elementen börjar från 0.</span><span class="sxs-lookup"><span data-stu-id="f4c34-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="f4c34-113">variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f4c34-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f4c34-114">En permutation av $n $-element som börjar från 0.</span><span class="sxs-lookup"><span data-stu-id="f4c34-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f4c34-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f4c34-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f4c34-116">En lista med $n $ qubits som permutationen tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="f4c34-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f4c34-117">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f4c34-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="f4c34-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="f4c34-118">Example</span></span>

<span data-ttu-id="f4c34-119">För att syntetisera en `SWAP` åtgärd:</span><span class="sxs-lookup"><span data-stu-id="f4c34-119">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecompositionWithVariableOrder([0, 2, 1, 3], [1, 0], LittleEndian(qubits));
}
```

## <a name="see-also"></a><span data-ttu-id="f4c34-120">Se även</span><span class="sxs-lookup"><span data-stu-id="f4c34-120">See Also</span></span>

- [<span data-ttu-id="f4c34-121">Microsoft. Quantum. syntes. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="f4c34-121">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="f4c34-122">Microsoft. Quantum. syntes. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="f4c34-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)