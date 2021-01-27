---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 2fbbe0d99ad1383d77cb08ff6b03bcebd8a1971f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852330"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="1bae2-102">PermuteQubits-åtgärd</span><span class="sxs-lookup"><span data-stu-id="1bae2-102">PermuteQubits operation</span></span>

<span data-ttu-id="1bae2-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1bae2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1bae2-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1bae2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1bae2-105">Permutes qubits med hjälp av VÄXLINGs åtgärden.</span><span class="sxs-lookup"><span data-stu-id="1bae2-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1bae2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1bae2-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="1bae2-107">ordning: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1bae2-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1bae2-108">Beskriver den nya ordningen för qubits där qubit vid indexet nu kommer att behållas [i].</span><span class="sxs-lookup"><span data-stu-id="1bae2-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="1bae2-109">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1bae2-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1bae2-110">Qubit-register att du ska handla på.</span><span class="sxs-lookup"><span data-stu-id="1bae2-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1bae2-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1bae2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="1bae2-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="1bae2-112">Example</span></span>

<span data-ttu-id="1bae2-113">Order = [2, 1, 0] och registrera $ \ket{\ alpha_0} \ket{\ alpha_1} \ket{\ alpha_2} $, PermuteQubits ändrar registret till $ \ket{\ alpha_2} \ket{\ alpha_1} \ket{\ alpha_0} $</span><span class="sxs-lookup"><span data-stu-id="1bae2-113">Given ordering = [2, 1, 0] and register $\ket{\alpha_0} \ket{\alpha_1} \ket{\alpha_2}$, PermuteQubits changes the register into $\ket{\alpha_2} \ket{\alpha_1} \ket{\alpha_0}$</span></span>

```qsharp
// The following two lines are equivalent
PermuteQubits([2, 1, 0], register);
SWAP(register[0], register[2]);
```