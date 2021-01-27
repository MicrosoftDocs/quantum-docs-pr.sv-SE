---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854575"
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