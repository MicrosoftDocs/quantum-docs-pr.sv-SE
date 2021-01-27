---
uid: Microsoft.Quantum.Convert.Call
title: Anrops åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850201"
---
# <a name="call-operation"></a>Anrops åtgärd

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Anropar en funktion med en specifik Indatatyp.

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>Description

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