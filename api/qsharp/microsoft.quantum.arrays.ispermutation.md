---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funktionen IsPermutation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730174"
---
# <a name="ispermutation-function"></a>Funktionen IsPermutation

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


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