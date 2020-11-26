---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Funktionen WithZeroInsertedAt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 414b703151b9152aa69709d9c28e68e5ae63506f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228873"
---
# <a name="withzeroinsertedat-function"></a>Funktionen WithZeroInsertedAt

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Infoga en 0-bit i ett heltal

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>Beskrivning

Den här åtgärden tar ett heltal, infogar en 0 vid bit `position` och returnerar det uppdaterade värdet som ett heltal.  Om du till exempel infogar 0 vid position 2 i talet 10 (10 USD _ {10} = 1010_ {2} $) returnerar talet 18 ($18 _ {10} = 10010_ {2} $).

## <a name="input"></a>Indata

### <a name="position--int"></a>position: [int](xref:microsoft.quantum.lang-ref.int)

Den position där 0 infogas


### <a name="value--int"></a>värde: [int](xref:microsoft.quantum.lang-ref.int)

Värdet som ändras



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Ändrat värde