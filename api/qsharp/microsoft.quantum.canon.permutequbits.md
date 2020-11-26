---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: deb5fa5b0bc0509c957e01bf22e491ad3e2214f3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205616"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="5b2f8-102">PermuteQubits-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5b2f8-102">PermuteQubits operation</span></span>

<span data-ttu-id="5b2f8-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5b2f8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5b2f8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5b2f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5b2f8-105">Permutes qubits med hjälp av VÄXLINGs åtgärden.</span><span class="sxs-lookup"><span data-stu-id="5b2f8-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5b2f8-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5b2f8-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="5b2f8-107">ordning: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5b2f8-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5b2f8-108">Beskriver den nya ordningen för qubits där qubit vid indexet nu kommer att behållas [i].</span><span class="sxs-lookup"><span data-stu-id="5b2f8-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="5b2f8-109">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5b2f8-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5b2f8-110">Qubit-register att du ska handla på.</span><span class="sxs-lookup"><span data-stu-id="5b2f8-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5b2f8-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5b2f8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

