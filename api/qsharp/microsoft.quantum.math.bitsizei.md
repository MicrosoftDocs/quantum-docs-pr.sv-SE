---
uid: Microsoft.Quantum.Math.BitSizeI
title: Funktionen BitSizeI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195859"
---
# <a name="bitsizei-function"></a>Funktionen BitSizeI

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


För ett icke-negativt heltal `a` returnerar antalet bitar som krävs för att representera `a` .

Det vill säga returnerar det minsta $n $ som $a < 2 ^ n $.

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a>Indata

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Det heltal vars bit-storlek ska beräknas.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Bit-storlek för `a` .