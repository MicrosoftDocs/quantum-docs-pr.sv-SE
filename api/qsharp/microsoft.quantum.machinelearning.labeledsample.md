---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846966"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="0bc99-102">LabeledSample-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="0bc99-102">LabeledSample user defined type</span></span>

<span data-ttu-id="0bc99-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0bc99-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0bc99-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0bc99-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="0bc99-105">Ett exempel som kallas för en klass som exemplet tillhör.</span><span class="sxs-lookup"><span data-stu-id="0bc99-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="0bc99-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="0bc99-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="0bc99-107">Funktioner: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0bc99-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0bc99-108">En Vector med funktioner för det aktuella exemplet.</span><span class="sxs-lookup"><span data-stu-id="0bc99-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="0bc99-109">Etikett: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0bc99-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0bc99-110">En heltals etikett för klassen som exemplet tillhör.</span><span class="sxs-lookup"><span data-stu-id="0bc99-110">An integer label for the class to which this sample belongs.</span></span>