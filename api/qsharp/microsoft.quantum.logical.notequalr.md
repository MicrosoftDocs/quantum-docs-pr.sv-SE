---
uid: Microsoft.Quantum.Logical.NotEqualR
title: Funktionen NotEqualR
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725968"
---
# <a name="notequalr-function"></a>Funktionen NotEqualR

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paketfilerna [](https://nuget.org/packages/)


Returnerar true om och endast om två indata är inte lika.

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Indata

### <a name="a--__invalidresult__"></a>a: __ogiltig <Result>__

Det första värdet som ska jämföras.


### <a name="b--__invalidresult__"></a>b: __ogiltigt <Result>__

Det andra värdet som ska jämföras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` om och endast om `a` inte är lika med `b` .

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```