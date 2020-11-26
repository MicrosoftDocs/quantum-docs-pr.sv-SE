---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funktionen IsPermutation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220934"
---
# <a name="ispermutation-function"></a>Funktionen IsPermutation

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utdata är true om och bara om en specifik matris representerar en permutation.

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>Beskrivning

`array`Med en längd mat ris `n` returneras TRUE om och endast om varje heltal från `0` ska `n - 1` visas exakt en gång i `array` , som `array` kan tolkas som en permutation i `n` element.

## <a name="input"></a>Indata

### <a name="permuation--int"></a>permuation: [int](xref:microsoft.quantum.lang-ref.int)[]

En matris som kan vara en permutation eller inte.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="remarks"></a>Kommentarer

En matris med längden noll är ett enkelt permutations värde.