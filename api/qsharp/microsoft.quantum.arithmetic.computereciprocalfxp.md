---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843250"
---
# <a name="computereciprocalfxp-operation"></a>ComputeReciprocalFxP-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Beräknar $1/x $ för ett fast punkt nummer $x $.

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="x--fixedpoint"></a>x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Fast punkts tal som ska inverteras.


### <a name="result--fixedpoint"></a>resultat: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Fast punkt nummer som ska innehålla resultatet. Måste initieras till $ \ket{0.0} $.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

