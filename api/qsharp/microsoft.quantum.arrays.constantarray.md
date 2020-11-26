---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: Funktionen ConstantArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210071"
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

