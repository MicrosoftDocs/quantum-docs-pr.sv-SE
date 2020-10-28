---
uid: Microsoft.Quantum.Math.PNorm
title: Funktionen PNorm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732246"
---
# <a name="pnorm-function"></a>Funktionen PNorm

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paketfilerna [](https://nuget.org/packages/)


Returnerar `L(p)` normen för en Vector of `Double` s.

Det vill säga att en matris $x $ av typ `Double[]` returnerar detta $p $-norm $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $.

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a>Indata

### <a name="p--double"></a>p: [dubbel](xref:microsoft.quantum.lang-ref.double)

Exponenten $p $ i $p $-norm.


### <a name="array--double"></a>matris: [dubbel](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)

$P $-norm $ \| x \| _p $.