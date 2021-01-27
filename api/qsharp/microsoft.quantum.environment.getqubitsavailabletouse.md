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
# <a name="getqubitsavailabletouse-operation"></a>GetQubitsAvailableToUse-åtgärd

Namnrymd: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Returnerar antalet qubits som för närvarande är tillgängliga för användning.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som kan allokeras i en `using` instruktion.
Om den måldator som används inte anger den här informationen `-1` returneras.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)