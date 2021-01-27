---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Funktionen Sequencer
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3cf09e48cce1aeb1aac837465ee3a5e06adf5169
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850994"
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

## <a name="example"></a>Exempel

```qsharp
let arr1 = SequenceI(0, 3); // [0, 1, 2, 3]
let arr2 = SequenceI(23, 29); // [23, 24, 25, 26, 27, 28, 29]
let arr3 = SequenceI(-5, -2); // [-5, -4, -3, -2]

let numbers = SequenceI(0, _); // function to create sequence from 0 to `to`
let naturals = SequenceI(1, _); // function to create sequence from 1 to `to`
```