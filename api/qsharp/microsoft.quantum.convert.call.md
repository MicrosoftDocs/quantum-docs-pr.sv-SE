---
uid: Microsoft.Quantum.Convert.Call
title: Anrops åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214219"
---
# <a name="call-operation"></a>Anrops åtgärd

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Anropar en funktion med en specifik Indatatyp.

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>Beskrivning

Med en funktion och indata till funktionen anropar funktionen och returnerar dess utdata.

## <a name="input"></a>Indata

### <a name="fn--input---output"></a>FN: "indata >"-utdata

En funktion som ska anropas.


### <a name="input--input"></a>inmatade: ' inmatare

Indatamängden som ska skickas till funktionen.



## <a name="output--output"></a>Utdata: utdata

Resultatet av anropet `fn` .

## <a name="type-parameters"></a>Typparametrar

### <a name="input"></a>' Inmatare


### <a name="output"></a>' Utdata



## <a name="remarks"></a>Kommentarer

Den här åtgärden är främst användbar för att tvinga en funktion att anropas på en viss plats i en åtgärd eller för att anropa en funktion där en åtgärd förväntas.