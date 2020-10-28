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
# <a name="getqubitsavailabletoborrow-operation"></a>GetQubitsAvailableToBorrow-åtgärd

Namnrymd: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Paketfilerna [](https://nuget.org/packages/)


Returnerar antalet qubits som för närvarande är tillgängliga för lån.
Detta inkluderar oanvända qubits; det vill säga detta inkluderar qubits som returnerades av `GetQubitsAvailableToUse` .

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som kan allokeras i en `borrowing` instruktion.
Om den måldator som används inte anger den här informationen `-1` returneras.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Environment. GetQubitsAvailableToUse](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)