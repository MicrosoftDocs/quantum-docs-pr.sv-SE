---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
title: OptimizedBEGeneratorSystem-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEGeneratorSystem
qsharp.summary: Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.
ms.openlocfilehash: 06d13a8a64a3c572821ec97f8776d6f1dbe4a4ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727744"
---
# <a name="optimizedbegeneratorsystem-user-defined-type"></a><span data-ttu-id="0ffa1-102">OptimizedBEGeneratorSystem-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="0ffa1-102">OptimizedBEGeneratorSystem user defined type</span></span>

<span data-ttu-id="0ffa1-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="0ffa1-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="0ffa1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0ffa1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0ffa1-105">Funktion som returnerar `OptimizedBETermIndex` data för term som `n` har fått ett heltal `n` , tillsammans med antalet termer i den första `Int` och summan av absoluta värden för alla term koefficienter i `Double` .</span><span class="sxs-lookup"><span data-stu-id="0ffa1-105">Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.</span></span>

```qsharp

newtype OptimizedBEGeneratorSystem = (Int, Double, (Int -> Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex));
```

