---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: Funktionen UncurriedOpC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728290"
---
# <a name="uncurriedopc-function"></a>Funktionen UncurriedOpC

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


En funktion som returnerar åtgärder returnerar en ny åtgärd som tar båda indata som en tupel.
Modifieraren `C` anger att åtgärderna är kontrollerbara.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Indata

### <a name="curriedop--t---u--unit-ctl"></a>curriedOp: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL

En funktion som returnerar åtgärder.



## <a name="output--tu--unit-ctl"></a>Utdata: (t) => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL

En ny åtgärd `op` som `op(t, u)` motsvarar `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för det första argumentet för en Curried-funktion.
### <a name="u"></a>' U

Typ av det andra argumentet för en Curried-funktion.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)