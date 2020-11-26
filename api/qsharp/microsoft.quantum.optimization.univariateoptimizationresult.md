---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194040"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult-användardefinierad typ

Namnrymd: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representerar resultatet av att optimera en univariate-funktion.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="coordinate--double"></a>Koordinat: [dubbel](xref:microsoft.quantum.lang-ref.double)

Indatamängden där en optimal hittades.
### <a name="value--double"></a>Värde: [Double](xref:microsoft.quantum.lang-ref.double)

Värde som returneras av funktionen i dess optimala.