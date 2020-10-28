---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: Funktionen LessThanOrEqualL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 333b76fc4885104e107dd25003a4e0dd5a9dd4af
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726022"
---
# <a name="lessthanorequall-function"></a>Funktionen LessThanOrEqualL

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paketfilerna [](https://nuget.org/packages/)


Returnerar true om och endast om ett tal är mindre än eller lika med ett annat tal.

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Indata

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Det första värdet som ska jämföras.


### <a name="b--bigint"></a>b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Det andra värdet som ska jämföras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` om och endast om `a` är mindre än eller lika med `b` .

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```