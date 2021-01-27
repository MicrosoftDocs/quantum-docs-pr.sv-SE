---
uid: Microsoft.Quantum.Math.PNormalized
title: Funktionen PNormalized
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854836"
---
# <a name="pnormalized-function"></a>Funktionen PNormalized

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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