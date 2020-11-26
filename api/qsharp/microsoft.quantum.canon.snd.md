---
uid: Microsoft.Quantum.Canon.Snd
title: SND-funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205328"
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