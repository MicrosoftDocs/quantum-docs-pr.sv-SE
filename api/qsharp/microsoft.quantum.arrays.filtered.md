---
uid: Microsoft.Quantum.Arrays.Filtered
title: Filtrerad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: fa8600f4d773daf6eabf8b9961ab46961155d1fd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221274"
---
# <a name="filtered-function"></a>Filtrerad funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med tanke på en matris och ett predikat som har definierats för elementen i matrisen, returnerar en matris som består av de element som uppfyller predikatet.

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Indata

### <a name="predicate--t---bool"></a>predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

En funktion från `'T` till boolesk som används för att filtrera element.


### <a name="array--t"></a>matris: ' ' []

En matris med element över `'T` .



## <a name="output--t"></a>Utdata: ' t []

En matris `'T[]` med element som uppfyller predikatet.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av `array` element.

## <a name="remarks"></a>Kommentarer

Funktionen definieras för generiska typer, d.v.s. När vi har en matris `'T[]` och ett predikat `'T -> Bool` kan vi filtrera element.