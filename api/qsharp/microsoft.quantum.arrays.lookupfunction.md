---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: Funktionen LookupFunction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730150"
---
# <a name="lookupfunction-function"></a>Funktionen LookupFunction

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


Med en matris returneras en funktion som returnerar element i matrisen.

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a>Indata

### <a name="array--t"></a>matris: ' ' []

Matrisen som ska visas som en lookup-funktion.



## <a name="output--int---t"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int) ->

En funktion `f` som `f(idx) == f[idx]` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av element i matrisen som representeras som en lookup-funktion.

## <a name="remarks"></a>Kommentarer

Den här funktionen är främst användbar för att samar beta med funktioner och åtgärder som utför `Int -> 'T` funktioner som argument. Detta är vanligt, t. ex. i Generator biblioteket, där Functions används för att undvika att behöva registrera en hel matris i minnet.