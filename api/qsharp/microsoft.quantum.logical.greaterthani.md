---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: Funktionen GreaterThanI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 86fc8e927c292a2ea814ed80a33de42bffdb96b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815945"
---
# <a name="greaterthani-function"></a>Funktionen GreaterThanI

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let cond = a > b;
let cond = GreaterThanI(a, b);
```