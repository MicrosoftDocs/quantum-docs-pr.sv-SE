---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Funktionen Sequence
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220271"
---
# <a name="sequencel-function"></a>Funktionen Sequence

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Hämta en matris med heltal inom ett angivet intervall.

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>Indata

### <a name="from--bigint"></a>från: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Ett inklusiv start index för intervallet.


### <a name="to--bigint"></a>till: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Ett partiellt slut index för intervallet som inte är mindre än `from` .



## <a name="output--bigint"></a>Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]

En matris som innehåller sekvensen med tal `from` , `from + 1` ,..., `to` .

## <a name="remarks"></a>Kommentarer

Skillnaden mellan `from` och `to` måste passa in i ett `Int` värde.