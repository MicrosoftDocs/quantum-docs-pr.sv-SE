---
uid: Microsoft.Quantum.Math.PNorm
title: Funktionen PNorm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 6207cca6cda5f9030facd31c327e58bdb9ecbf14
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847658"
---
# <a name="pnorm-function"></a>Funktionen PNorm

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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