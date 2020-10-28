---
uid: Microsoft.Quantum.Canon.Snd
title: SND-funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728392"
---
# <a name="snd-function"></a>SND-funktion

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paketfilerna [](https://nuget.org/packages/)


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