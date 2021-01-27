---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: Funktionen ResultArrayAsBoolArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 384531137474562ebc8cc24dcd1ac976dc91ad9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832599"
---
# <a name="resultarrayasboolarray-function"></a>Funktionen ResultArrayAsBoolArray

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konverterar en `Result[]` typ till en `Bool[]` typ, där `One` mappas till `true` och `Zero` mappas till `false` .

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a>Indata

### <a name="input--__invalidresult__"></a>inmatade: __ogiltigt <Result>__[]

`Result[]` som ska konverteras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]

En `Bool[]` som representerar `input` .