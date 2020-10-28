---
uid: Microsoft.Quantum.Logical.Conditioned
title: Conditionisk funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731294"
---
# <a name="conditioned-function"></a>Conditionisk funktion

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paketfilerna [](https://nuget.org/packages/)


Returnerar ett av två värden, beroende på värdet för ett booleskt villkor.

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a>Indata

### <a name="condition--bool"></a>villkor: [bool](xref:microsoft.quantum.lang-ref.bool)

Ett villkor som används för att styra vilka indatatyper som returneras.


### <a name="iftrue--t"></a>ifTrue: ' t

Värdet som ska returneras när `condition` är `true` .


### <a name="iffalse--t"></a>ifFalse: ' t

Värdet som ska returneras när `condition` är `false` .



## <a name="output--t"></a>Utdata: ' t

`ifTrue` Om `condition` är `true` , och `ifFalse` annars.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="remarks"></a>Kommentarer

Till skillnad från `?|` operatorn är den här funktionen inte en kort krets, så att båda indatana utvärderas fullständigt.

Till följd av kort slutning är följande motsvarigheter:

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```