---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: Funktionen UncurriedOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728302"
---
# <a name="uncurriedop-function"></a>Funktionen UncurriedOp

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


En funktion som returnerar åtgärder returnerar en ny åtgärd som tar båda indata som en tupel.

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a>Indata

### <a name="curriedop--t---u--unit"></a>curriedOp: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En funktion som returnerar åtgärder.



## <a name="output--tu--unit"></a>Utdata: (, ' U) => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En ny åtgärd `op` som `op(t, u)` motsvarar `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för den första indatamängden till en Curried-åtgärd.
### <a name="u"></a>' U

Typen för den andra ingången till en Curried-åtgärd.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. UncurriedOpC](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [Microsoft. Quantum. Canon. UncurriedOpA](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [Microsoft. Quantum. Canon. UncurriedOpCA](xref:Microsoft.Quantum.Canon.UncurriedOpCA)