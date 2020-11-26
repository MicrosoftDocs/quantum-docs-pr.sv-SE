---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203322"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="a21ba-102">ApplyTransposition-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a21ba-102">ApplyTransposition operation</span></span>

<span data-ttu-id="a21ba-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a21ba-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a21ba-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a21ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a21ba-105">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a21ba-105">Description</span></span>

<span data-ttu-id="a21ba-106">Den här åtgärden byter till amplituden vid indexet `a` med amplituden vid indexet `b` i det aktuella tillståndets vektor med `register` längden $n $.</span><span class="sxs-lookup"><span data-stu-id="a21ba-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="a21ba-107">Om `a` det är lika med `b` ändras inte tillstånds vektorn.</span><span class="sxs-lookup"><span data-stu-id="a21ba-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="a21ba-108">Indata</span><span class="sxs-lookup"><span data-stu-id="a21ba-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a21ba-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a21ba-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a21ba-110">Första index (måste vara ett värde mellan 0 och $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="a21ba-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="a21ba-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a21ba-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a21ba-112">Andra indexet (måste vara ett värde mellan 0 och $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="a21ba-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="a21ba-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a21ba-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a21ba-114">En lista över $n $ qubits som införlivaren tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="a21ba-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a21ba-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a21ba-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

