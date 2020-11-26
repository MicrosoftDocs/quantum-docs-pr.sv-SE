---
uid: Microsoft.Quantum.Canon.OperationPowC
title: Funktionen OperationPowC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 71f66dd0098ab58d327fc33dbe5af191df0d3dc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205736"
---
# <a name="operationpowc-function"></a>Funktionen OperationPowC

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Genererar en åtgärd till en exponent.
Modifieraren `C` anger att åtgärden är kontrollerbar.

Det vill säga en åtgärd som representerar en grind $U $, returnerar en ny åtgärd $U ^ m $ för en Power $m $.

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a>Indata

### <a name="op--t--unit--is-ctl"></a>OP: t => [enheten](xref:microsoft.quantum.lang-ref.unit)  är CTL

En åtgärd $U $ som representerar den port som ska upprepas.


### <a name="power--int"></a>effekt: [int](xref:microsoft.quantum.lang-ref.int)

Antalet gånger som $U $ ska upprepas.



## <a name="output--t--unit--is-ctl"></a>Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL

En ny åtgärd som representerar $U ^ m $, där $m = \texttt{Power} $.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av åtgärd som ska användas.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)