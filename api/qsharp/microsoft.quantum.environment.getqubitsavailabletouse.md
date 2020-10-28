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
# <a name="getqubitsavailabletouse-operation"></a>GetQubitsAvailableToUse-åtgärd

Namnrymd: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Paketfilerna [](https://nuget.org/packages/)


Returnerar antalet qubits som för närvarande är tillgängliga för användning.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som kan allokeras i en `using` instruktion.
Om den måldator som används inte anger den här informationen `-1` returneras.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)