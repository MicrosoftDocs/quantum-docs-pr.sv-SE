---
uid: Microsoft.Quantum.Math.Fraction
title: Användardefinierad typ av fraktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733022"
---
# <a name="fraction-user-defined-type"></a>Användardefinierad typ av fraktion

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paketfilerna [](https://nuget.org/packages/)


Representerar ett rationellt antal formulär `p/q` . Integer `p` är det första elementet i tuppeln och `q` är det andra elementet i tuppeln.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="numerator--int"></a>Täljare: [int](xref:microsoft.quantum.lang-ref.int)

Täljare för bråket.
### <a name="denominator--int"></a>Nämnare: [int](xref:microsoft.quantum.lang-ref.int)

Nämnaren för bråk/