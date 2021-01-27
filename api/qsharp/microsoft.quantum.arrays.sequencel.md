---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Funktionen Sequence
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850990"
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

## <a name="example"></a>Exempel

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a>Kommentarer

Skillnaden mellan `from` och `to` måste passa in i ett `Int` värde.