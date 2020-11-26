---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: Funktionen LookupFunction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: db20795719d11138cbdc5a38c0a19d0f247af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220781"
---
# <a name="lookupfunction-function"></a>Funktionen LookupFunction

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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