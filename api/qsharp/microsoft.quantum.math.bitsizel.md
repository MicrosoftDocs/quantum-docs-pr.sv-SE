---
uid: Microsoft.Quantum.Math.BitSizeL
title: Funktionen BitSizeL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 97068f12050317a9aa17c95f33650ef6f406066d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732755"
---
# <a name="bitsizel-function"></a>Funktionen BitSizeL

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paketfilerna [](https://nuget.org/packages/)


För ett icke-negativt heltal `a` returnerar antalet bitar som krävs för att representera `a` .

Det vill säga returnerar det minsta $n $ som $a < 2 ^ n $.

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a>Indata

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Det heltal vars bit-storlek ska beräknas.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Bit-storlek för `a` .