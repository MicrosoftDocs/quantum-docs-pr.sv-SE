---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855569"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="dd05d-102">ApplyTransposition-åtgärd</span><span class="sxs-lookup"><span data-stu-id="dd05d-102">ApplyTransposition operation</span></span>

<span data-ttu-id="dd05d-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="dd05d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="dd05d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd05d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="dd05d-105">Description</span><span class="sxs-lookup"><span data-stu-id="dd05d-105">Description</span></span>

<span data-ttu-id="dd05d-106">Den här åtgärden byter till amplituden vid indexet `a` med amplituden vid indexet `b` i det aktuella tillståndets vektor med `register` längden $n $.</span><span class="sxs-lookup"><span data-stu-id="dd05d-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="dd05d-107">Om `a` det är lika med `b` ändras inte tillstånds vektorn.</span><span class="sxs-lookup"><span data-stu-id="dd05d-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="dd05d-108">Indata</span><span class="sxs-lookup"><span data-stu-id="dd05d-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="dd05d-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd05d-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd05d-110">Första index (måste vara ett värde mellan 0 och $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="dd05d-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="dd05d-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd05d-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd05d-112">Andra indexet (måste vara ett värde mellan 0 och $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="dd05d-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="dd05d-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dd05d-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="dd05d-114">En lista över $n $ qubits som införlivaren tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="dd05d-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dd05d-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd05d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="dd05d-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="dd05d-116">Example</span></span>

<span data-ttu-id="dd05d-117">Förbered en enhetlig överplacering av nummer tillstånden $ | 1 \ rangle $, $ | 2 \ rangle $ och $ | 3 \ rangle $ på 2 qubits.</span><span class="sxs-lookup"><span data-stu-id="dd05d-117">Prepare a uniform superposition of number states $|1\rangle$, $|2\rangle$, and $|3\rangle$ on 2 qubits.</span></span>

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```