---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: Funktionen ExtendedGreatestCommonDivisorI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 8cb21ae5052ae6c5a8aed8be71d6bd3d32034272
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733059"
---
# <a name="extendedgreatestcommondivisori-function"></a>Funktionen ExtendedGreatestCommonDivisorI

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paketfilerna [](https://nuget.org/packages/)


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