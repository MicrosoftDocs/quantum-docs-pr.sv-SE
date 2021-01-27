---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: Funktionen IsNotZero
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839603"
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