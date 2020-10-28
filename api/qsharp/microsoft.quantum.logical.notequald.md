---
uid: Microsoft.Quantum.Logical.NotEqualD
title: Funktionen NotEqualD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dd21fcc1d0d73bd210303bfbf4f336386b912107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732918"
---
# <a name="notequald-function"></a>Funktionen NotEqualD

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paketfilerna [](https://nuget.org/packages/)


Returnerar true om och endast om två indata är inte lika.

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Indata

### <a name="a--double"></a>a: [Double](xref:microsoft.quantum.lang-ref.double)

Det första värdet som ska jämföras.


### <a name="b--double"></a>b: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det andra värdet som ska jämföras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` om och endast om `a` inte är lika med `b` .

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```