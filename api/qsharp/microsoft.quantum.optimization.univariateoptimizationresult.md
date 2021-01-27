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
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="d3838-102">UnivariateOptimizationResult-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="d3838-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="d3838-103">Namnrymd: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="d3838-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="d3838-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3838-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3838-105">Representerar resultatet av att optimera en univariate-funktion.</span><span class="sxs-lookup"><span data-stu-id="d3838-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="d3838-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="d3838-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="d3838-107">Koordinat: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d3838-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d3838-108">Indatamängden där en optimal hittades.</span><span class="sxs-lookup"><span data-stu-id="d3838-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="d3838-109">Värde: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d3838-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d3838-110">Värde som returneras av funktionen i dess optimala.</span><span class="sxs-lookup"><span data-stu-id="d3838-110">Value returned by the function at its optimum.</span></span>