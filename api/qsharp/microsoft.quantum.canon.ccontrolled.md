---
uid: Microsoft.Quantum.Canon.CControlled
title: Funktionen CControlled
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: f4d91471eae859b7018c9e7ea0c1c853619c484d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841014"
---
# <a name="ccontrolled-function"></a>Funktionen CControlled

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en åtgärd op returnerar en ny åtgärd som tillämpar op om en klassisk kontroll bit är sann. Om `false` händer ingenting.

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a>Indata

### <a name="op--t--unit"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En åtgärd som ska tillämpas villkorligt.



## <a name="output--boolt--unit"></a>Utdata: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En ny åtgärd som är OP om den klassiska kontroll biten är true.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd som ska tillämpas villkorligt.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. CControlledC](xref:Microsoft.Quantum.Canon.CControlledC)
- [Microsoft. Quantum. Canon. CControlledA](xref:Microsoft.Quantum.Canon.CControlledA)
- [Microsoft. Quantum. Canon. CControlledCA](xref:Microsoft.Quantum.Canon.CControlledCA)