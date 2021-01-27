---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: Funktionen UncurriedOpC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 05df99dce8b167f32078ce256748647ceb94d0fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851995"
---
# <a name="uncurriedopc-function"></a>Funktionen UncurriedOpC

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


En funktion som returnerar åtgärder returnerar en ny åtgärd som tar båda indata som en tupel.
Modifieraren `C` anger att åtgärderna är kontrollerbara.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Indata

### <a name="curriedop--t---u--unit--is-ctl"></a>curriedOp: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL

En funktion som returnerar åtgärder.



## <a name="output--tu--unit--is-ctl"></a>Utdata: (, ' U) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL

En ny åtgärd `op` som `op(t, u)` motsvarar `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för det första argumentet för en Curried-funktion.
### <a name="u"></a>' U

Typ av det andra argumentet för en Curried-funktion.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)