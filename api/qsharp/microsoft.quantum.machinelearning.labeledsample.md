---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196335"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="5b42c-102">LabeledSample-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="5b42c-102">LabeledSample user defined type</span></span>

<span data-ttu-id="5b42c-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5b42c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="5b42c-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5b42c-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="5b42c-105">Ett exempel som kallas för en klass som exemplet tillhör.</span><span class="sxs-lookup"><span data-stu-id="5b42c-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="5b42c-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="5b42c-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="5b42c-107">Funktioner: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5b42c-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="5b42c-108">En Vector med funktioner för det aktuella exemplet.</span><span class="sxs-lookup"><span data-stu-id="5b42c-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="5b42c-109">Etikett: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5b42c-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5b42c-110">En heltals etikett för klassen som exemplet tillhör.</span><span class="sxs-lookup"><span data-stu-id="5b42c-110">An integer label for the class to which this sample belongs.</span></span>