---
uid: Microsoft.Quantum.Arrays.IndexOf
title: Funktionen IndexOf
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848513"
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



## <a name="example"></a>Exempel

Anta att `IsEven : Int -> Bool` är en funktion som returnerar `true` om och bara om indatatypen är till och med. Sedan kan du använda `IndexOf` för att hitta det första elementet till och med en matris:

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```