---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Funktionen WithZeroInsertedAt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855200"
---
# <a name="withzeroinsertedat-function"></a>Funktionen WithZeroInsertedAt

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Infoga en 0-bit i ett heltal

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>Description

Den här åtgärden tar ett heltal, infogar en 0 vid bit `position` och returnerar det uppdaterade värdet som ett heltal.  Om du till exempel infogar 0 vid position 2 i talet 10 (10 USD _ {10} = 1010_ {2} $) returnerar talet 18 ($18 _ {10} = 10010_ {2} $).

## <a name="input"></a>Indata

### <a name="position--int"></a>position: [int](xref:microsoft.quantum.lang-ref.int)

Den position där 0 infogas


### <a name="value--int"></a>värde: [int](xref:microsoft.quantum.lang-ref.int)

Värdet som ändras



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Ändrat värde