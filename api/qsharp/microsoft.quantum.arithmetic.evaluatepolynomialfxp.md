---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: EvaluatePolynomialFxP-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: d88f9002f4ce39b6a16091837c76168fb3a2f086
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843212"
---
# <a name="evaluatepolynomialfxp-operation"></a>EvaluatePolynomialFxP-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Utvärderar en polynom i en fast punkts representation.

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="coefficients--double"></a>koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]

Koefficienter för polynomen som en dubbel matris, d.v.s. matrisen $ [a_0, a_1,..., a_d] $ för polynom $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.


### <a name="fpx--fixedpoint"></a>FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Inmatat punkt nummer för vilket polynomen ska utvärderas.


### <a name="result--fixedpoint"></a>resultat: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Anger ett fast punkt-värde för utdata som innehåller $P (x) $. Måste vara i tillstånd $ \ket {0} $ initialt.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

