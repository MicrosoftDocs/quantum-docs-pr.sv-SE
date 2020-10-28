---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727162"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="2ab4d-102">GetQubitsAvailableToUse-åtgärd</span><span class="sxs-lookup"><span data-stu-id="2ab4d-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="2ab4d-103">Namnrymd: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="2ab4d-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="2ab4d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2ab4d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2ab4d-105">Returnerar antalet qubits som för närvarande är tillgängliga för användning.</span><span class="sxs-lookup"><span data-stu-id="2ab4d-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="2ab4d-106">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2ab4d-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2ab4d-107">Antalet qubits som kan allokeras i en `using` instruktion.</span><span class="sxs-lookup"><span data-stu-id="2ab4d-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="2ab4d-108">Om den måldator som används inte anger den här informationen `-1` returneras.</span><span class="sxs-lookup"><span data-stu-id="2ab4d-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ab4d-109">Se även</span><span class="sxs-lookup"><span data-stu-id="2ab4d-109">See Also</span></span>

- [<span data-ttu-id="2ab4d-110">Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="2ab4d-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)