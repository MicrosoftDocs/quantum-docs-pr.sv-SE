---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: f2294fadb9c10d800b7a743fbfe0810f36f18516
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853252"
---
# <a name="getqubitsavailabletoborrow-operation"></a>GetQubitsAvailableToBorrow-åtgärd

Namnrymd: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Returnerar antalet qubits som för närvarande är tillgängliga för lån.

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som kan lånas och inte allokeras som en del av en `borrowing` instruktion.
Om den måldator som används inte anger den här informationen `-1` returneras.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Environment. GetQubitsAvailableToUse](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)