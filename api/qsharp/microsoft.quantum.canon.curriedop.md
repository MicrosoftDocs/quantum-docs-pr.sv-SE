---
uid: Microsoft.Quantum.Canon.CurriedOp
title: Funktionen CurriedOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: f811347d65a6460690163e9df631979c906bd89f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840773"
---
# <a name="curriedop-function"></a>Funktionen CurriedOp

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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