---
uid: Microsoft.Quantum.Arrays.EqualA
title: Likhets funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848695"
---
# <a name="equala-function"></a>Likhets funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Exempel

Följande kod kontrollerar om olika par av matriser är lika:

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a>Kommentarer

Den här funktionen definieras för generiska typer. det vill säga när vi har två matriser `'T[]` och en funktion `equal: ('T, 'T) -> Bool` , returnerar den här funktionen ett `Bool` värde som anger om matriserna är lika.
För att två matriser ska anses vara lika måste de ha samma längd och elementen i samma positioner i matriserna måste vara identiska.