---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732766"
---
# <a name="bigfraction-user-defined-type"></a>BigFraction-användardefinierad typ

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paketfilerna [](https://nuget.org/packages/)


Representerar ett rationellt antal formulär `p/q` . Integer `p` är det första elementet i tuppeln och `q` är det andra elementet i tuppeln.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="numerator--bigint"></a>Täljare: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Täljare för bråket.
### <a name="denominator--bigint"></a>Nämnare: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Nämnaren för bråk/