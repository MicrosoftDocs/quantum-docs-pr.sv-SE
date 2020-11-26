---
uid: Microsoft.Quantum.Math.Fraction
title: Användardefinierad typ av fraktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210683"
---
# <a name="fraction-user-defined-type"></a>Användardefinierad typ av fraktion

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representerar ett rationellt antal formulär `p/q` . Integer `p` är det första elementet i tuppeln och `q` är det andra elementet i tuppeln.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="numerator--int"></a>Täljare: [int](xref:microsoft.quantum.lang-ref.int)

Täljare för bråket.
### <a name="denominator--int"></a>Nämnare: [int](xref:microsoft.quantum.lang-ref.int)

Nämnaren för bråk/