---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Funktionen Sequence
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730022"
---
# <a name="sequencel-function"></a>Funktionen Sequence

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


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