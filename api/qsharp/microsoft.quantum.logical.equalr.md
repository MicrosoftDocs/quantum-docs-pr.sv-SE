---
uid: Microsoft.Quantum.Logical.EqualR
title: Likhets funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d68b2f1a26bf318400d3c88b37d9aabcc38cbdfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198014"
---
# <a name="equalr-function"></a>Likhets funktion

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar true om och bara om två indata är lika.

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Indata

### <a name="a--__invalidresult__"></a>a: __ogiltig <Result>__

Det första värdet som ska jämföras.


### <a name="b--__invalidresult__"></a>b: __ogiltigt <Result>__

Det andra värdet som ska jämföras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` om och bara om `a` är lika med `b` .

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```