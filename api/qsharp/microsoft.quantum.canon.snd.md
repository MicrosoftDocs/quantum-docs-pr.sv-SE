---
uid: Microsoft.Quantum.Canon.Snd
title: SND-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: 11786fa195de12a7f2e4f2edb00ac0bc1071dd5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852158"
---
# <a name="snd-function"></a>SND-funktion

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ett annat element returneras av ett par.

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a>Indata

### <a name="pair--tu"></a>par: (t. ex. ' U)

En tupel med två element.



## <a name="output--u"></a>Utdata: ' U

Det andra elementet i `pair` .

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av parets första medlem.
### <a name="u"></a>' U

Typ av parets andra medlem.