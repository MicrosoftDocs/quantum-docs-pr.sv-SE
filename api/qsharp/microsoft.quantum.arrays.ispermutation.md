---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funktionen IsPermutation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848097"
---
# <a name="ispermutation-function"></a>Funktionen IsPermutation

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utdata är true om och bara om en specifik matris representerar en permutation.

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>Description

`array`Med en längd mat ris `n` returneras TRUE om och endast om varje heltal från `0` ska `n - 1` visas exakt en gång i `array` , som `array` kan tolkas som en permutation i `n` element.

## <a name="input"></a>Indata

### <a name="permuation--int"></a>permuation: [int](xref:microsoft.quantum.lang-ref.int)[]

En matris som kan vara en permutation eller inte.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="example"></a>Exempel

Följande Q #-kod skriver ut meddelandet "all diagnostik har slutförts":

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a>Kommentarer

En matris med längden noll är ett enkelt permutations värde.