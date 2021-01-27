---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: Funktionen ConstantArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846229"
---
# <a name="constantarray-function"></a>Funktionen ConstantArray

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Skapar en matris med angiven längd med alla element som motsvarar det aktuella värdet.

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>Indata

### <a name="length--int"></a>Längd: [int](xref:microsoft.quantum.lang-ref.int)

Längden på den nya matrisen.


### <a name="value--t"></a>värde: ' t

Värdet för varje element i den nya matrisen.



## <a name="output--t"></a>Utdata: ' t []

En ny längd mat ris `length` , t. ex. varje element `value` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="example"></a>Exempel

Följande kod skapar en matris med tre booleska värden, var och en som motsvarar `true` :

```qsharp
let array = ConstantArray(3, true);
```