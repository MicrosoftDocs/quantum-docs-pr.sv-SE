---
uid: Microsoft.Quantum.Math.BitSizeI
title: Funktionen BitSizeI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7edf37a81571dfa1d4cb755493e1863a44c694e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857703"
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