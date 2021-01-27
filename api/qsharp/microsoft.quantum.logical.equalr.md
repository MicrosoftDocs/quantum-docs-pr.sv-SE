---
uid: Microsoft.Quantum.Logical.EqualR
title: Likhets funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 9ce29f2868f092001a3dca23a2913a3963ac70fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815980"
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

```qsharp
let cond = a == b;
let cond = EqualR(a, b);
```