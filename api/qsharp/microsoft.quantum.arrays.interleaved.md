---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Överlagrad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848119"
---
# <a name="interleaved-function"></a>Överlagrad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Överlåter två matriser av (nästan) samma storlek.

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a>Description

Den här funktionen returnerar Interfoliering av två matriser, som börjar med det första elementet från den första matrisen, sedan det första elementet från den andra matrisen och så vidare.

Den första matrisen måste antingen vara av samma längd som den andra, eller ha ett annat element.

## <a name="input"></a>Indata

### <a name="first--t"></a>första: ' ' []

Den första matrisen som ska överlåtas.


### <a name="second--t"></a>sekund: ' t []

Den andra matrisen som ska överlåtas.



## <a name="output--t"></a>Utdata: ' t []

Överlagrad matris

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för varje element i `first` och `second` .

## <a name="example"></a>Exempel

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```