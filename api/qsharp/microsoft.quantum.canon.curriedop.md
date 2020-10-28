---
uid: Microsoft.Quantum.Canon.CurriedOp
title: Funktionen CurriedOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 13bc3e195d8a4ba26b726f96e4dc6b83da43c3e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728785"
---
# <a name="curriedop-function"></a>Funktionen CurriedOp

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Returnerar en Curried-version för en åtgärd på två indata.

Det vill säga en åtgärd med två indata, använder den här funktionen curry isomorphism $f (x, y) \equiv f (x) $ för att returnera en åtgärd av en indata som returnerar en åtgärd av en indata.

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a>Indata

### <a name="op--tu--unit"></a>OP: (, ' U) => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En åtgärd vars indatamängd är ett par.



## <a name="output--t---u--unit"></a>Utdata: ' t-> ' U => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En åtgärd som accepterar det första elementet i ett par och returnerar en åtgärd som accepterar den andra delen av den ursprungliga åtgärdens Indatatyp.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för den första komponenten i en funktion som definieras i par.
### <a name="u"></a>' U

Typen för den andra komponenten i en funktion som definieras i par.

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```