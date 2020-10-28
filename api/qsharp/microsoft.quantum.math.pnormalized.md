---
uid: Microsoft.Quantum.Math.PNormalized
title: Funktionen PNormalized
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732238"
---
# <a name="pnormalized-function"></a>Funktionen PNormalized

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paketfilerna [](https://nuget.org/packages/)


Normaliserar en Vector of `Double` s i `L(p)` normen.

Det vill säga, med en matris $x $ av typen `Double[]` , returnerar detta en matris där alla element delas av $p $-norm $ \| x \| _p $.

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a>Indata

### <a name="p--double"></a>p: [dubbel](xref:microsoft.quantum.lang-ref.double)

Exponenten $p $ i $p $-norm.


### <a name="array--double"></a>matris: [dubbel](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrisen $x $ normaliseras av $p $-norm $ \| x \| _p $.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Math. PNorm](xref:Microsoft.Quantum.Math.PNorm)