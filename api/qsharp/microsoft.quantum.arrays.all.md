---
uid: Microsoft.Quantum.Arrays.All
title: All-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 17e61ea161b90fe089b7df7c10188d604d72dcfa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842900"
---
# <a name="all-function"></a>All-funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tilldelas en matris och ett predikat som har definierats för elementen i matrisen och kontrollerar om alla element i matrisen uppfyller predikatet.

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Indata

### <a name="predicate--t---bool"></a>predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

En funktion från `'T` till `Bool` som används för att kontrol lera element.


### <a name="array--t"></a>matris: ' ' []

En matris med element över `'T` .



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

Ett `Bool` värde på-och-funktionen för predikatet som används för alla element.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av `array` element.

## <a name="example"></a>Exempel

Följande kod kontrollerar om alla element i matrisen inte är noll:

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function AllDemo() : Unit {
    let predicate = NotEqualI(_, 0);
    let isNonZero = All(predicate, [2, 3, 4, 5, 6, 0]);
    Message($"{isNonZero}");
}
```

## <a name="remarks"></a>Kommentarer

Funktionen definieras för generiska typer, d.v.s. När vi har en matris `'T[]` och en funktion `predicate: 'T -> Bool` kan vi skapa ett `Bool` värde som anger om alla element uppfyller `predicate` .