---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Funktionen Sequencer
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730035"
---
# <a name="sequencei-function"></a>Funktionen Sequencer

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


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