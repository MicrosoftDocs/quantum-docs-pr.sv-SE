---
uid: Microsoft.Quantum.Arrays.EqualA
title: Likhets funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730294"
---
# <a name="equala-function"></a>Likhets funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


Två matriser av samma typ och ett predikat som har definierats för par element i matriserna, kontrollerar om matriserna är lika.

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a>Indata

### <a name="equal--tt---bool"></a>lika med: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

En funktion från tupel `('T, 'T)` till `Bool` som används för att kontrol lera om två element i matriser är lika.


### <a name="array1--t"></a>matris1: ' t []

Den första matrisen som ska jämföras.


### <a name="array2--t"></a>matris2: ' t []

Den andra matrisen som ska jämföras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

Värdet `true` IF och endast IF `array1` och `array2` är lika med.
Det vill säga om båda matriserna har samma längd och alla element är lika definierade som de av `equal` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för varje mat ris element.

## <a name="remarks"></a>Kommentarer

Den här funktionen definieras för generiska typer. det vill säga när vi har två matriser `'T[]` och en funktion `equal: ('T, 'T) -> Bool` , returnerar den här funktionen ett `Bool` värde som anger om matriserna är lika.
För att två matriser ska anses vara lika måste de ha samma längd och elementen i samma positioner i matriserna måste vara identiska.