---
uid: Microsoft.Quantum.Logical.LessThanI
title: Funktionen LessThanI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 69c3d7c414967b830c15189c895a2b34f409c7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815824"
---
# <a name="lessthani-function"></a>Funktionen LessThanI

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar true om och endast om ett tal är mindre än ett annat tal.

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Indata

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Det första värdet som ska jämföras.


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Det andra värdet som ska jämföras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` om och bara om `a` är strikt mindre än `b` .

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```qsharp
let cond = a < b;
let cond = LessThanI(a, b);
```