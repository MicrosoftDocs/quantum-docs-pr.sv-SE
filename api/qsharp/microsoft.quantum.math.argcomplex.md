---
uid: Microsoft.Quantum.Math.ArgComplex
title: Funktionen ArgComplex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 259296f397207cde4a7d6dfe6cfb1a18e8055216
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211108"
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