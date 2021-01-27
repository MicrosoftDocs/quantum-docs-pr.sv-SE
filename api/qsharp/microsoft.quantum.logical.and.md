---
uid: Microsoft.Quantum.Logical.And
title: Och-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 6c405bdb4182cc7f32bd04952dec25a974c03445
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849233"
---
# <a name="and-function"></a>Och-funktion

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar den booleska samningen av två värden.

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Indata

### <a name="a--bool"></a>a: [bool](xref:microsoft.quantum.lang-ref.bool)

Det första värdet som ska beaktas.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Det andra värdet som ska beaktas.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` om och endast om `a` och `b` är båda `true` .

## <a name="remarks"></a>Kommentarer

Till skillnad från `and` operatorn är den här funktionen inte en kort krets, så att båda indatana utvärderas fullständigt.

Till följd av kort slutning är följande motsvarigheter:

```qsharp
let x = a and b;
let x = And(a, b);
```