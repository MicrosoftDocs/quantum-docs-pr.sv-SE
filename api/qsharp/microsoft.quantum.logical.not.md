---
uid: Microsoft.Quantum.Logical.Not
title: Fungerar inte
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197457"
---
# <a name="not-function"></a>Fungerar inte

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar den booleska negationen av ett värde.

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a>Indata

### <a name="value--bool"></a>värde: [bool](xref:microsoft.quantum.lang-ref.bool)

Värdet som ska vara negationt.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` om och bara om `value` är `false` .

## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```Q#
let x = not value;
let x = Not(value);
```