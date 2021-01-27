---
uid: Microsoft.Quantum.Canon.Delayed
title: Fördröjd funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 40fcc7d0a178fdb18437b4d6c96542db593347b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840590"
---
# <a name="delayed-function"></a>Fördröjd funktion

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en åtgärd som tillämpar den åtgärd som har angivet argument.

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a>Indata

### <a name="op--t--u"></a>OP: t => ' U 

En åtgärd som ska tillämpas.


### <a name="arg--t"></a>arg: ' t

De indatatyper som åtgärden tillämpas på.



## <a name="output--unit--u"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit) => ' U 

En ny åtgärd som gäller `op` för inmatade `arg`

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd som ska fördröjas.
### <a name="u"></a>' U

Retur typen för åtgärden som ska fördröjas.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. DelayedC](xref:Microsoft.Quantum.Canon.DelayedC)
- [Microsoft. Quantum. Canon. försenat](xref:Microsoft.Quantum.Canon.DelayedA)
- [Microsoft. Quantum. Canon. DelayedCA](xref:Microsoft.Quantum.Canon.DelayedCA)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)