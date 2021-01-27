---
uid: Microsoft.Quantum.Logical.LessThanD
title: Funktionen LessThanD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 7135ed4b3414d143f5020496ae524bf89980a8a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849160"
---
# <a name="lessthand-function"></a>Funktionen LessThanD

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar true om och endast om ett tal är mindre än ett annat tal.

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Indata

### <a name="a--double"></a>a: [Double](xref:microsoft.quantum.lang-ref.double)

Det första värdet som ska jämföras.


### <a name="b--double"></a>b: [dubbel](xref:microsoft.quantum.lang-ref.double)

Det andra värdet som ska jämföras.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` om och bara om `a` är strikt mindre än `b` .

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```qsharp
let cond = a < b;
let cond = LessThanD(a, b);
```