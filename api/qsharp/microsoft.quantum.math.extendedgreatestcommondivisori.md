---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: Funktionen ExtendedGreatestCommonDivisorI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 365e91e84add0d57d5a3cf203bbf23d96979b251
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195535"
---
# <a name="extendedgreatestcommondivisori-function"></a>Funktionen ExtendedGreatestCommonDivisorI

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Beräknar en tupel $ (u, v) $ så att $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, där $ \operatorname{GCD} $ är $a $ största gemensamma divisor av $a $ och $b $. GCD är alltid positivt.

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a>Indata

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

det första antalet som utökade största gemensamma divisor beräknas


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

det andra antalet som utökade största gemensamma divisor beräknas



## <a name="output--intint"></a>Utdata: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

Tupel $ (u, v) $ med egenskapen $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.

## <a name="references"></a>Referenser

- Den här implementeringen sker enligt https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm