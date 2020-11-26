---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: Funktionen FunctionAsOperation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224385"
---
# <a name="functionasoperation-function"></a>Funktionen FunctionAsOperation

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konverterar funktioner till åtgärder.

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>Beskrivning

Med en funktion returnerar en åtgärd som anropar funktionen och som inte gör något annat.

## <a name="input"></a>Indata

### <a name="fn--input---output"></a>FN: "indata >"-utdata

En funktion som ska konverteras till en åtgärd.



## <a name="output--input--output"></a>Output: ' indata => ' utdata 

En åtgärd `op` som `op(input)` är identisk med `fn(input)` för alla `input` .

## <a name="type-parameters"></a>Typparametrar

### <a name="input"></a>' Inmatare

Indatatypen för funktionen som ska konverteras.
### <a name="output"></a>' Utdata

Utdatatypen för funktionen som ska konverteras.

## <a name="remarks"></a>Kommentarer

Detta är främst användbart för att skicka funktioner till Functions eller åtgärder som förväntar sig en åtgärd som indatamängd.