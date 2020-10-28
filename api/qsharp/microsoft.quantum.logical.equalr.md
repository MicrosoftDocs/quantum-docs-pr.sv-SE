---
uid: Microsoft.Quantum.Logical.EqualR
title: Likhets funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726070"
---
# <a name="equalr-function"></a>Likhets funktion

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paketfilerna [](https://nuget.org/packages/)


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