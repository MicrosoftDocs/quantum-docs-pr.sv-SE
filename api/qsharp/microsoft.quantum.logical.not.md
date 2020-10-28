---
uid: Microsoft.Quantum.Logical.Not
title: Fungerar inte
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725998"
---
# <a name="not-function"></a>Fungerar inte

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paketfilerna [](https://nuget.org/packages/)


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