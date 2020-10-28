---
uid: Microsoft.Quantum.Canon.Compose
title: Funktionen Skriv
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728839"
---
# <a name="compose-function"></a>Funktionen Skriv

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


Returnerar sammansättningen för två functions.

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>Beskrivning

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