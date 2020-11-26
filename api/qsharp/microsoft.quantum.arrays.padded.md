---
uid: Microsoft.Quantum.Arrays.Padded
title: Utfylld funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 2b7a80d1cf5c82a1ff52bc4aa207cfe335b40061
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220543"
---
# <a name="padded-function"></a>Utfylld funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en matris som är utfyllnadad vid med angivna värden upp till en angiven längd.

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a>Indata

### <a name="nelementstotal--int"></a>nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)

Längden på den utfyllda matrisen. Om detta är positivt `inputArray` fylls huvudet i på huvudet. Om detta är negativt `inputArray` fylls det i på slutet.


### <a name="defaultelement--t"></a>defaultElement: ' t

Standardvärde som ska användas för fyllnads element.


### <a name="inputarray--t"></a>inputArray: inte []

Matris vars värden finns i huvudet i den utgående matrisen.



## <a name="output--t"></a>Utdata: ' t []

En matris `output` som är `inputArray` utfylld i huvudet med `defaultElement` s fram till `output` längden `nElementsTotal`

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av mat ris element.