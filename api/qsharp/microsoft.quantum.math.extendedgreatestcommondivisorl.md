---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: Funktionen ExtendedGreatestCommonDivisorL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e671405045d6d2587a8c6ccbac4ae3402f92f722
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733054"
---
# <a name="extendedgreatestcommondivisorl-function"></a>Funktionen ExtendedGreatestCommonDivisorL

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paketfilerna [](https://nuget.org/packages/)


Beräknar en tupel $ (u, v) $ så att $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, där $ \operatorname{GCD} $ är $a $ största gemensamma divisor av $a $ och $b $. GCD är alltid positivt.

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a>Indata

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

det första antalet som utökade största gemensamma divisor beräknas


### <a name="b--bigint"></a>b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

det andra antalet som utökade största gemensamma divisor beräknas



## <a name="output--bigintbigint"></a>Utdata: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))

Tupel $ (u, v) $ med egenskapen $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.

## <a name="references"></a>Referenser

- Den här implementeringen sker enligt https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm