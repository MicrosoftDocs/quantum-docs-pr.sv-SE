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
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="90eb0-102">UnivariateOptimizationResult-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="90eb0-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="90eb0-103">Namnrymd: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="90eb0-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="90eb0-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="90eb0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="90eb0-105">Representerar resultatet av att optimera en univariate-funktion.</span><span class="sxs-lookup"><span data-stu-id="90eb0-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="90eb0-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="90eb0-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="90eb0-107">Koordinat: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="90eb0-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="90eb0-108">Indatamängden där en optimal hittades.</span><span class="sxs-lookup"><span data-stu-id="90eb0-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="90eb0-109">Värde: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="90eb0-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="90eb0-110">Värde som returneras av funktionen i dess optimala.</span><span class="sxs-lookup"><span data-stu-id="90eb0-110">Value returned by the function at its optimum.</span></span>