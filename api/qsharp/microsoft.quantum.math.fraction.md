---
uid: Microsoft.Quantum.Math.Fraction
title: Användardefinierad typ av fraktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857520"
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