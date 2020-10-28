---
uid: Microsoft.Quantum.Logical.And
title: Och-funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731302"
---
# <a name="and-function"></a>Och-funktion

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paketfilerna [](https://nuget.org/packages/)


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

```Q#
let x = a and b;
let x = And(a, b);
```