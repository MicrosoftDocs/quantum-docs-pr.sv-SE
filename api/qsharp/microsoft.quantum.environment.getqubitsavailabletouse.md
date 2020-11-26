---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201418"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="b3bad-102">GetQubitsAvailableToUse-åtgärd</span><span class="sxs-lookup"><span data-stu-id="b3bad-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="b3bad-103">Namnrymd: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="b3bad-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="b3bad-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b3bad-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b3bad-105">Returnerar antalet qubits som för närvarande är tillgängliga för användning.</span><span class="sxs-lookup"><span data-stu-id="b3bad-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="b3bad-106">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b3bad-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b3bad-107">Antalet qubits som kan allokeras i en `using` instruktion.</span><span class="sxs-lookup"><span data-stu-id="b3bad-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="b3bad-108">Om den måldator som används inte anger den här informationen `-1` returneras.</span><span class="sxs-lookup"><span data-stu-id="b3bad-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3bad-109">Se även</span><span class="sxs-lookup"><span data-stu-id="b3bad-109">See Also</span></span>

- [<span data-ttu-id="b3bad-110">Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="b3bad-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)