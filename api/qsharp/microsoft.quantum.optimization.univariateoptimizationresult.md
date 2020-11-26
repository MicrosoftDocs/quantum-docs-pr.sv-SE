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
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="a9597-102">UnivariateOptimizationResult-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="a9597-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="a9597-103">Namnrymd: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="a9597-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="a9597-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a9597-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a9597-105">Representerar resultatet av att optimera en univariate-funktion.</span><span class="sxs-lookup"><span data-stu-id="a9597-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="a9597-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="a9597-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="a9597-107">Koordinat: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a9597-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a9597-108">Indatamängden där en optimal hittades.</span><span class="sxs-lookup"><span data-stu-id="a9597-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="a9597-109">Värde: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a9597-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a9597-110">Värde som returneras av funktionen i dess optimala.</span><span class="sxs-lookup"><span data-stu-id="a9597-110">Value returned by the function at its optimum.</span></span>