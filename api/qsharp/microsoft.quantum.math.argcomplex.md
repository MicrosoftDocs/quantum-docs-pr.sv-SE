---
uid: Microsoft.Quantum.Math.ArgComplex
title: Funktionen ArgComplex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732798"
---
# <a name="argcomplex-function"></a>Funktionen ArgComplex

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paketfilerna [](https://nuget.org/packages/)


Returnerar fasen för ett komplext tal av typen `Complex` .

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Indata

### <a name="input--complex"></a>inmatade: [komplexa](xref:Microsoft.Quantum.Math.Complex)

Komplext tal $c = x + i y $.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)

Fas $ \text{Arg} [c] = \text{ArcTan} (y, x) \in (-\pi, \pi] $.