---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: Funktionen OperationPowCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 338c40f8eb9d6f1782989f2a91c86df561d480bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852315"
---
# <a name="operationpowca-function"></a>Funktionen OperationPowCA

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Genererar en åtgärd till en exponent.
Modifieraren `A` anger att åtgärden är kontrollerbar och adjointable.

Det vill säga en åtgärd som representerar en grind $U $, returnerar en ny åtgärd $U ^ m $ för en Power $m $.

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>Indata

### <a name="op--t--unit--is-adj--ctl"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En åtgärd $U $ som representerar den port som ska upprepas.


### <a name="power--int"></a>effekt: [int](xref:microsoft.quantum.lang-ref.int)

Antalet gånger som $U $ ska upprepas.



## <a name="output--t--unit--is-adj--ctl"></a>Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En ny åtgärd som representerar $U ^ m $, där $m = \texttt{Power} $.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av åtgärd som ska användas.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)