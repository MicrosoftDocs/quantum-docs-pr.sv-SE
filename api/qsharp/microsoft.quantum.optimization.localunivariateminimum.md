---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: Funktionen LocalUnivariateMinimum
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: 3b09af88bbed20a392768d005e5e9567b3bb7022
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726493"
---
# <a name="localunivariateminimum-function"></a>Funktionen LocalUnivariateMinimum

Namnrymd: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Paketfilerna [](https://nuget.org/packages/)


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