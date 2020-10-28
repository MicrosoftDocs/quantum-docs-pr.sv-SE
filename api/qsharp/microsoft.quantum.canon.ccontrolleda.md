---
uid: Microsoft.Quantum.Canon.CControlledA
title: Funktionen CControlledA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728878"
---
# <a name="ccontrolleda-function"></a>Funktionen CControlledA

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Med en åtgärd op returnerar en ny åtgärd som tillämpar op om en klassisk kontroll bit är sann. Om `false` händer ingenting.
Modifieraren `A` anger att åtgärden är adjointable.

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a>Indata

### <a name="op--t--unit-adj"></a>OP: t => [enhets](xref:microsoft.quantum.lang-ref.unit) justering

En åtgärd som ska tillämpas villkorligt.



## <a name="output--boolt--unit-adj"></a>Utdata: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering

En ny åtgärd som är OP om den klassiska kontroll biten är true.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd som ska tillämpas villkorligt.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)