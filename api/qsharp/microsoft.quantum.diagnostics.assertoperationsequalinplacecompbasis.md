---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: AssertOperationsEqualInPlaceCompBasis-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: f9d3aaf7e774cf2495ca69382db2470d1d0fa7b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830486"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a><span data-ttu-id="e7ba3-102">AssertOperationsEqualInPlaceCompBasis-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e7ba3-102">AssertOperationsEqualInPlaceCompBasis operation</span></span>

<span data-ttu-id="e7ba3-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e7ba3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e7ba3-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e7ba3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e7ba3-105">Kontrollerar om åtgärden `givenU` är lika med åtgärden `expectedU` för den angivna indata-storleken genom att kontrol lera åtgärdens åtgärder endast på vektorerna från beräknings basen.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-105">Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis.</span></span>
<span data-ttu-id="e7ba3-106">Detta är ett nödvändigt, men inte tillräckligt, villkor för likheten av två unitaries.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-106">This is a necessary, but not sufficient, condition for the equality of two unitaries.</span></span>

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="e7ba3-107">Indata</span><span class="sxs-lookup"><span data-stu-id="e7ba3-107">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="e7ba3-108">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7ba3-108">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e7ba3-109">Antalet qubits-$n $ som driften `givenU` och `expectedU` arbetar med.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-109">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="e7ba3-110">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e7ba3-110">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e7ba3-111">Åtgärden på $n $ qubits ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-111">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="e7ba3-112">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="e7ba3-112">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e7ba3-113">Referens åtgärd på $n $ qubits som ska `givenU` jämföras med.</span><span class="sxs-lookup"><span data-stu-id="e7ba3-113">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e7ba3-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e7ba3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

