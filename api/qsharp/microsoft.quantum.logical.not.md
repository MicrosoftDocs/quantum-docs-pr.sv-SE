---
uid: Microsoft.Quantum.Logical.Not
title: Fungerar inte
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849081"
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

```qsharp
let x = not value;
let x = Not(value);
```