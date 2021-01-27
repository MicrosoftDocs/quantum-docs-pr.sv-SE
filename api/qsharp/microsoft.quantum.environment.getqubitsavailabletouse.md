---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827805"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="f4ea9-102">GetQubitsAvailableToUse-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f4ea9-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="f4ea9-103">Namnrymd: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="f4ea9-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="f4ea9-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f4ea9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f4ea9-105">Returnerar antalet qubits som för närvarande är tillgängliga för användning.</span><span class="sxs-lookup"><span data-stu-id="f4ea9-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="f4ea9-106">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4ea9-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4ea9-107">Antalet qubits som kan allokeras i en `using` instruktion.</span><span class="sxs-lookup"><span data-stu-id="f4ea9-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="f4ea9-108">Om den måldator som används inte anger den här informationen `-1` returneras.</span><span class="sxs-lookup"><span data-stu-id="f4ea9-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4ea9-109">Se även</span><span class="sxs-lookup"><span data-stu-id="f4ea9-109">See Also</span></span>

- [<span data-ttu-id="f4ea9-110">Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="f4ea9-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)