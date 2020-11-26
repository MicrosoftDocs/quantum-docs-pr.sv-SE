---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: Funktionen IsNotZero
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204070"
---
# <a name="isnotzero-function"></a>Funktionen IsNotZero

Namnrymd: [Microsoft. Quantum. kemi](xref:Microsoft.Quantum.Chemistry)

Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Kontrollerar om ett `Double` tal inte är ungefär noll.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Indata

### <a name="number--double"></a>nummer: [dubbel](xref:microsoft.quantum.lang-ref.double)

Antal som ska kontrol leras



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

Returnerar true om `number` har ett absolut värde som är större än `1e-15` .