---
uid: Microsoft.Quantum.Canon.Fst
title: Funktionen FST
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840520"
---
# <a name="fst-function"></a>Funktionen FST

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Baserat på ett par, returnerar det första elementet.

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a>Indata

### <a name="pair--tu"></a>par: (t. ex. ' U)

En tupel med två element.



## <a name="output--t"></a>Utdata: ' t

Det första elementet i `pair` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av parets första medlem.
### <a name="u"></a>' U

Typ av parets andra medlem.