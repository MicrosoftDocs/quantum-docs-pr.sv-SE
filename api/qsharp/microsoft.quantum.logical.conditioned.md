---
uid: Microsoft.Quantum.Logical.Conditioned
title: Conditionisk funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817292"
---
# <a name="conditioned-function"></a>Conditionisk funktion

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```