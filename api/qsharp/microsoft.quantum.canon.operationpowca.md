---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: Funktionen OperationPowCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728488"
---
# <a name="operationpowca-function"></a>Funktionen OperationPowCA

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Genererar en åtgärd till en exponent.
Modifieraren `A` anger att åtgärden är kontrollerbar och adjointable.

Det vill säga en åtgärd som representerar en grind $U $, returnerar en ny åtgärd $U ^ m $ för en Power $m $.

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>Indata

### <a name="op--t--unit-ctl--adj"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL + just

En åtgärd $U $ som representerar den port som ska upprepas.


### <a name="power--int"></a>effekt: [int](xref:microsoft.quantum.lang-ref.int)

Antalet gånger som $U $ ska upprepas.



## <a name="output--t--unit-ctl--adj"></a>Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL + just

En ny åtgärd som representerar $U ^ m $, där $m = \texttt{Power} $.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av åtgärd som ska användas.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)