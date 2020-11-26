---
uid: Microsoft.Quantum.Arrays.Any
title: Alla funktioner
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: 717ab9ebcbb864a6faf1c14cd36125e589849f2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221665"
---
# <a name="any-function"></a>Alla funktioner

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en matris och ett predikat som har definierats för elementen i matrisen, kontrollerar om minst ett element i matrisen uppfyller predikatet.

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Indata

### <a name="predicate--t---bool"></a>predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

En funktion från `'T` till `Bool` som används för att kontrol lera element.


### <a name="array--t"></a>matris: ' ' []

En matris med element över `'T` .



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

Ett `Bool` värde på eller-funktionen för predikatet som används för alla element.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av `array` element.

## <a name="remarks"></a>Kommentarer

Funktionen definieras för generiska typer, dvs. När vi har en matris `'T[]` och en funktion `predicate: 'T -> Bool` kan vi skapa ett `Bool` värde som anger om ett element uppfyller sig `predicate` .