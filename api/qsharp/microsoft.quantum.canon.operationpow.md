---
uid: Microsoft.Quantum.Canon.OperationPow
title: Funktionen OperationPow
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 808001200d276ca21cc5a70140d5d84d96da3496
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205821"
---
# <a name="operationpow-function"></a>Funktionen OperationPow

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Genererar en åtgärd till en exponent.

Det vill säga en åtgärd som representerar en grind $U $, returnerar en ny åtgärd $U ^ m $ för en Power $m $.

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a>Indata

### <a name="op--t--unit"></a>OP: t => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En åtgärd $U $ som representerar den port som ska upprepas.


### <a name="power--int"></a>effekt: [int](xref:microsoft.quantum.lang-ref.int)

Antalet gånger som $U $ ska upprepas.



## <a name="output--t--unit"></a>Utdata: t => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En ny åtgärd som representerar $U ^ m $, där $m = \texttt{Power} $.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av åtgärd som ska användas.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. OperationPowC](xref:Microsoft.Quantum.Canon.OperationPowC)
- [Microsoft. Quantum. Canon. OperationPowA](xref:Microsoft.Quantum.Canon.OperationPowA)
- [Microsoft. Quantum. Canon. OperationPowCA](xref:Microsoft.Quantum.Canon.OperationPowCA)