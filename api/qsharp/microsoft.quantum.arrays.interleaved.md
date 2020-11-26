---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Överlagrad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220968"
---
# <a name="interleaved-function"></a>Överlagrad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Överlåter två matriser av (nästan) samma storlek.

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a>Beskrivning

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