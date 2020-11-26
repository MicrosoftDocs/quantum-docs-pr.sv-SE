---
uid: Microsoft.Quantum.Arrays.IndexOf
title: Funktionen IndexOf
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: d63b204334611f8f2c3860f9ee1d756f637780e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221019"
---
# <a name="indexof-function"></a>Funktionen IndexOf

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar det första indexet för det första elementet i en matris som uppfyller ett angivet predikat. Returnerar-1 om det inte finns något sådant element.

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>Indata

### <a name="predicate--t---bool"></a>predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

En predika funktion som fungerar på element i matrisen.


### <a name="arr--t"></a>arr: ' t []

En matris som ska genomsökas med det aktuella predikatet.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Antingen det minsta indexet `idx` som `predicate(arr[idx])` är sant eller-1 om det inte finns något sådant element.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

