---
uid: Microsoft.Quantum.Arrays.Padded
title: Utfylld funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845570"
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

## <a name="example"></a>Exempel

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```