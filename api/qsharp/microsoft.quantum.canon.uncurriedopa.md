---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: Funktionen UncurriedOpA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: e535d017d2665ddb76e5f422e18b8656c73171c6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204631"
---
# <a name="uncurriedopa-function"></a>Funktionen UncurriedOpA

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


En funktion som returnerar åtgärder returnerar en ny åtgärd som tar båda indata som en tupel.
Modifieraren `A` anger att åtgärderna är adjointable.

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a>Indata

### <a name="curriedop--t---u--unit--is-adj"></a>curriedOp: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

En funktion som returnerar åtgärder.



## <a name="output--tu--unit--is-adj"></a>Utdata: (, ' U) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

En ny åtgärd `op` som `op(t, u)` motsvarar `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för det första argumentet för en Curried-funktion.
### <a name="u"></a>' U

Typ av det andra argumentet för en Curried-funktion.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)