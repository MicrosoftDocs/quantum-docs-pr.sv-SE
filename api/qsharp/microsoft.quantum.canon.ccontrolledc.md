---
uid: Microsoft.Quantum.Canon.CControlledC
title: Funktionen CControlledC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 25ac2b35047b1c33a89149eae6d40f6f7ae3b454
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216922"
---
# <a name="ccontrolledc-function"></a>Funktionen CControlledC

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en åtgärd op returnerar en ny åtgärd som tillämpar op om en klassisk kontroll bit är sann. Om `false` händer ingenting.
Modifieraren `C` anger att åtgärden är kontrollerbar.

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a>Indata

### <a name="op--t--unit--is-ctl"></a>OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL

En åtgärd som ska tillämpas villkorligt.



## <a name="output--boolt--unit--is-ctl"></a>Utdata: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL

En ny åtgärd som är OP om den klassiska kontroll biten är true.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den åtgärd som ska tillämpas villkorligt.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)