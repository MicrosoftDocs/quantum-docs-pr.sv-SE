---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211091"
---
# <a name="bigfraction-user-defined-type"></a>BigFraction-användardefinierad typ

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representerar ett rationellt antal formulär `p/q` . Integer `p` är det första elementet i tuppeln och `q` är det andra elementet i tuppeln.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="numerator--bigint"></a>Täljare: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Täljare för bråket.
### <a name="denominator--bigint"></a>Nämnare: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Nämnaren för bråk/