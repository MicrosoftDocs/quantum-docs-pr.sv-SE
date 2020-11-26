---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Funktionen Sequencer
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220305"
---
# <a name="sequencei-function"></a>Funktionen Sequencer

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Hämta en matris med heltal inom ett angivet intervall.

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a>Indata

### <a name="from--int"></a>från: [int](xref:microsoft.quantum.lang-ref.int)

Ett inklusiv start index för intervallet.


### <a name="to--int"></a>till: [int](xref:microsoft.quantum.lang-ref.int)

Ett partiellt slut index för intervallet som inte är mindre än `from` .



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]

En matris som innehåller sekvensen med tal `from` , `from + 1` ,..., `to` .