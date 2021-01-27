---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: c3129cb796a344f7ad38a585183db285d48892bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843238"
---
# <a name="evaluateevenpolynomialfxp-operation"></a>EvaluateEvenPolynomialFxP-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Utvärderar en jämn polynom i en fast punkts representation.

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="coefficients--double"></a>koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]

Koefficienter för jämnt polynomed som en dubbel matris, d.v.s. matrisen $ [a_0, a_1,..., a_k] $ för den jämnt polynom $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2} $.


### <a name="fpx--fixedpoint"></a>FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Inmatat punkt nummer för vilket polynomen ska utvärderas.


### <a name="result--fixedpoint"></a>resultat: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Anger ett fast punkt-värde för utdata som innehåller $P (x) $. Måste vara i tillstånd $ \ket {0} $ initialt.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

