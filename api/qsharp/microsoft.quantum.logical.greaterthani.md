---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: Funktionen GreaterThanI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: ffd00d8086654a2d783a351fe254fb2ee35b9184
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726049"
---
# <a name="greaterthani-function"></a>Funktionen GreaterThanI

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paketfilerna [](https://nuget.org/packages/)


Returnerar true om och endast om ett tal är större än ett annat tal.

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Indata

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Det första värdet som ska jämföras.


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Det andra värdet som ska jämföras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` om och bara om `a` är strikt större än `b` .

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```