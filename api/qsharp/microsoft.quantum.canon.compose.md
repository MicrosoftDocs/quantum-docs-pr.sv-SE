---
uid: Microsoft.Quantum.Canon.Compose
title: Funktionen Skriv
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840914"
---
# <a name="compose-function"></a>Funktionen Skriv

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar sammansättningen för två functions.

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>Description

Två Functions $f $ och $g $ returnerar en ny funktion som representerar $f \circ g $.

## <a name="input"></a>Indata

### <a name="outer--u---v"></a>yttre: "U->" V

Den andra funktionen som ska användas.


### <a name="inner--t---u"></a>inre: ' t-> ' U

Den första funktionen som ska användas.



## <a name="output--t---v"></a>Utdata: ' t-> ' V

En ny funktion $h $ t. ex. för alla indata $x $, $f (g (x)) = h (x) $.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Indatatypen för den första funktionen som ska användas.
### <a name="u"></a>' U

Utdatatypen för den första funktionen som ska användas och indatatypen för den andra funktionen som ska användas.
### <a name="v"></a>' V

Utdatatypen för den andra funktionen som ska användas.