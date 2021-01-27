---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: Funktionen UncurriedOpCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 910d8a3006a2f217888b791e479e10f9f1a6965e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840043"
---
# <a name="uncurriedopca-function"></a>Funktionen UncurriedOpCA

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


En funktion som returnerar åtgärder returnerar en ny åtgärd som tar båda indata som en tupel.
Modifieraren `CA` anger att åtgärderna är kontrollerbara och adjointable.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Indata

### <a name="curriedop--t---u--unit--is-adj--ctl"></a>curriedOp: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En funktion som returnerar åtgärder.



## <a name="output--tu--unit--is-adj--ctl"></a>Utdata: (t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En ny åtgärd `op` som `op(t, u)` motsvarar `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för det första argumentet för en Curried-funktion.
### <a name="u"></a>' U

Typ av det andra argumentet för en Curried-funktion.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)