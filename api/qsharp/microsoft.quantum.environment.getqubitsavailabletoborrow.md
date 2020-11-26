---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: 30b97c2b6e1353f008d085c3bae6160763557c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201469"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="17bdc-102">GetQubitsAvailableToBorrow-åtgärd</span><span class="sxs-lookup"><span data-stu-id="17bdc-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="17bdc-103">Namnrymd: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="17bdc-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="17bdc-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="17bdc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="17bdc-105">Returnerar antalet qubits som för närvarande är tillgängliga för lån.</span><span class="sxs-lookup"><span data-stu-id="17bdc-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="17bdc-106">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="17bdc-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="17bdc-107">Antalet qubits som kan lånas och inte allokeras som en del av en `borrowing` instruktion.</span><span class="sxs-lookup"><span data-stu-id="17bdc-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="17bdc-108">Om den måldator som används inte anger den här informationen `-1` returneras.</span><span class="sxs-lookup"><span data-stu-id="17bdc-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="17bdc-109">Se även</span><span class="sxs-lookup"><span data-stu-id="17bdc-109">See Also</span></span>

- [<span data-ttu-id="17bdc-110">Microsoft. Quantum. Environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="17bdc-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)