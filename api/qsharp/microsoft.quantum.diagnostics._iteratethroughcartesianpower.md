---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: _iterateThroughCartesianPower åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: a27302be75ee701b0629310700b56d222aaef7db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853567"
---
# <a name="_iteratethroughcartesianpower-operation"></a>_iterateThroughCartesianPower åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Itererar en variabel genom en kartesiska-produkt [0, gränser [0]-1] × [0, gränser [1]-1] × [0, gränser [längd (gränser)-1]-1] och anrop OP (arr) för varje element i kartesiska-produkten

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a>Indata

### <a name="length--int"></a>Längd: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="value--int"></a>värde: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--int--unit"></a>OP: [int](xref:microsoft.quantum.lang-ref.int)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) 





## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

