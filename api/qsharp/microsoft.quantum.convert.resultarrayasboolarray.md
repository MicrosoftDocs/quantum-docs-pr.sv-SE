---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: Funktionen ResultArrayAsBoolArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 0356fe9c98306ee3e1857f4af311aef9b3789a7d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727495"
---
# <a name="resultarrayasboolarray-function"></a>Funktionen ResultArrayAsBoolArray

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paketfilerna [](https://nuget.org/packages/)


Konverterar en `Result[]` typ till en `Bool[]` typ, där `One` mappas till `true` och `Zero` mappas till `false` .

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a>Indata

### <a name="input--__invalidresult__"></a>inmatade: __ogiltigt <Result>__ []

`Result[]` som ska konverteras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]

En `Bool[]` som representerar `input` .