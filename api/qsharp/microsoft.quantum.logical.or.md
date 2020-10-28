---
uid: Microsoft.Quantum.Logical.Or
title: Eller funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730755"
---
# <a name="or-function"></a>Eller funktion

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paketfilerna [](https://nuget.org/packages/)


Returnerar den booleska disknuten av två värden.

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Indata

### <a name="a--bool"></a>a: [bool](xref:microsoft.quantum.lang-ref.bool)

Det första värdet som ska beaktas.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Det andra värdet som ska beaktas.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` om och endast om antingen `a` eller `b` `true` .

## <a name="remarks"></a>Kommentarer

Till skillnad från `or` operatorn är den här funktionen inte en kort krets, så att båda indatana utvärderas fullständigt.

Till följd av kort slutning är följande motsvarigheter:

```Q#
let x = a or b;
let x = Or(a, b);
```