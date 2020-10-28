---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733403"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult-användardefinierad typ

Namnrymd: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Paketfilerna [](https://nuget.org/packages/)


Representerar resultatet av att optimera en univariate-funktion.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="coordinate--double"></a>Koordinat: [dubbel](xref:microsoft.quantum.lang-ref.double)

Indatamängden där en optimal hittades.
### <a name="value--double"></a>Värde: [Double](xref:microsoft.quantum.lang-ref.double)

Värde som returneras av funktionen i dess optimala.