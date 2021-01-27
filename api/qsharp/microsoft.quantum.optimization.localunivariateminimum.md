---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: Funktionen LocalUnivariateMinimum
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854600"
---
# <a name="localunivariateminimum-function"></a>Funktionen LocalUnivariateMinimum

Namnrymd: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar det lokala minimivärdet för en univariate-funktion under ett begränsat intervall med hjälp av en gyllene intervalls ökning.

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a>Indata

### <a name="fn--double---double"></a>FN: [dubbel](xref:microsoft.quantum.lang-ref.double) -> [dubbel](xref:microsoft.quantum.lang-ref.double)

Univariate-funktionen som ska minimeras.


### <a name="bounds--doubledouble"></a>gränser: ([dubbel](xref:microsoft.quantum.lang-ref.double),[dubbel](xref:microsoft.quantum.lang-ref.double))

Intervallet som det lokala minimivärdet ska hittas i.


### <a name="tolerance--double"></a>tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)

Noggrannheten i funktionen indatatyper som ska tolereras.
Sökningen efter lokal OPTIMA fortsätter tills intervallet är mindre än denna tolerans.



## <a name="output--univariateoptimizationresult"></a>Utdata: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)

En lokal OPTIMA för den aktuella funktionen, som finns inom de tilldelade gränserna.