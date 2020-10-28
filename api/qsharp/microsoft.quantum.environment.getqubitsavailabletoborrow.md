---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727165"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="6d6aa-102">GetQubitsAvailableToBorrow-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6d6aa-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="6d6aa-103">Namnrymd: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="6d6aa-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="6d6aa-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6d6aa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6d6aa-105">Returnerar antalet qubits som för närvarande är tillgängliga för lån.</span><span class="sxs-lookup"><span data-stu-id="6d6aa-105">Returns the number of qubits currently available to borrow.</span></span>
<span data-ttu-id="6d6aa-106">Detta inkluderar oanvända qubits; det vill säga detta inkluderar qubits som returnerades av `GetQubitsAvailableToUse` .</span><span class="sxs-lookup"><span data-stu-id="6d6aa-106">This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="6d6aa-107">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6d6aa-107">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6d6aa-108">Antalet qubits som kan allokeras i en `borrowing` instruktion.</span><span class="sxs-lookup"><span data-stu-id="6d6aa-108">The number of qubits that could be allocated in a `borrowing` statement.</span></span>
<span data-ttu-id="6d6aa-109">Om den måldator som används inte anger den här informationen `-1` returneras.</span><span class="sxs-lookup"><span data-stu-id="6d6aa-109">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d6aa-110">Se även</span><span class="sxs-lookup"><span data-stu-id="6d6aa-110">See Also</span></span>

- [<span data-ttu-id="6d6aa-111">Microsoft. Quantum. Environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="6d6aa-111">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)