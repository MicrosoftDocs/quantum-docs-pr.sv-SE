---
uid: Microsoft.Quantum.Math.ArgComplex
title: Funktionen ArgComplex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: e8ce73a43940ab0ed66338f962cc6f76fc2b694b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842762"
---
# <a name="argcomplex-function"></a>Funktionen ArgComplex

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar fasen för ett komplext tal av typen `Complex` .

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Indata

### <a name="input--complex"></a>inmatade: [komplexa](xref:Microsoft.Quantum.Math.Complex)

Komplext tal $c = x + i y $.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)

Fas $ \text{Arg} [c] = \text{ArcTan} (y, x) \in (-\pi, \pi] $.