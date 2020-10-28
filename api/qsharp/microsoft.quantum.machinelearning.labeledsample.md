---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726628"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="305d1-102">LabeledSample-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="305d1-102">LabeledSample user defined type</span></span>

<span data-ttu-id="305d1-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="305d1-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="305d1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="305d1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="305d1-105">Ett exempel som kallas för en klass som exemplet tillhör.</span><span class="sxs-lookup"><span data-stu-id="305d1-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="305d1-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="305d1-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="305d1-107">Funktioner: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="305d1-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="305d1-108">En Vector med funktioner för det aktuella exemplet.</span><span class="sxs-lookup"><span data-stu-id="305d1-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="305d1-109">Etikett: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="305d1-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="305d1-110">En heltals etikett för klassen som exemplet tillhör.</span><span class="sxs-lookup"><span data-stu-id="305d1-110">An integer label for the class to which this sample belongs.</span></span>