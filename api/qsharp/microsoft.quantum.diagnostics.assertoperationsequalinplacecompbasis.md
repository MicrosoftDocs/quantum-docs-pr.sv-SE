---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: AssertOperationsEqualInPlaceCompBasis-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: 3275680f86ca2a178c7f044b97d226fe41c3186c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727327"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a><span data-ttu-id="4e55d-102">AssertOperationsEqualInPlaceCompBasis-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4e55d-102">AssertOperationsEqualInPlaceCompBasis operation</span></span>

<span data-ttu-id="4e55d-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4e55d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4e55d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e55d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e55d-105">Kontrollerar om åtgärden `givenU` är lika med åtgärden `expectedU` för den angivna indata-storleken genom att kontrol lera åtgärdens åtgärder endast på vektorerna från beräknings basen.</span><span class="sxs-lookup"><span data-stu-id="4e55d-105">Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis.</span></span>
<span data-ttu-id="4e55d-106">Detta är ett nödvändigt, men inte tillräckligt, villkor för likheten av två unitaries.</span><span class="sxs-lookup"><span data-stu-id="4e55d-106">This is a necessary, but not sufficient, condition for the equality of two unitaries.</span></span>

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="4e55d-107">Indata</span><span class="sxs-lookup"><span data-stu-id="4e55d-107">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="4e55d-108">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4e55d-108">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4e55d-109">Antalet qubits-$n $ som driften `givenU` och `expectedU` arbetar med.</span><span class="sxs-lookup"><span data-stu-id="4e55d-109">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="4e55d-110">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e55d-110">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4e55d-111">Åtgärden på $n $ qubits ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="4e55d-111">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="4e55d-112">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="4e55d-112">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4e55d-113">Referens åtgärd på $n $ qubits som ska `givenU` jämföras med.</span><span class="sxs-lookup"><span data-stu-id="4e55d-113">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4e55d-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e55d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

