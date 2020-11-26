---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Funktionen för felklassificering
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211686"
---
# <a name="misclassifications-function"></a><span data-ttu-id="a2f50-102">Funktionen för felklassificering</span><span class="sxs-lookup"><span data-stu-id="a2f50-102">Misclassifications function</span></span>

<span data-ttu-id="a2f50-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a2f50-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a2f50-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a2f50-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a2f50-105">Om du har fått en uppsättning av uppskjutna etiketter och en uppsättning korrekta etiketter, returnerar index för var varje uppsättning etiketter skiljer sig.</span><span class="sxs-lookup"><span data-stu-id="a2f50-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="a2f50-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a2f50-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="a2f50-107">inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a2f50-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a2f50-108">Etiketter härledda för en angiven utbildning eller validerings uppsättning.</span><span class="sxs-lookup"><span data-stu-id="a2f50-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="a2f50-109">actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a2f50-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a2f50-110">De sanna etiketterna för en angiven utbildning eller verifierings uppsättning.</span><span class="sxs-lookup"><span data-stu-id="a2f50-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="a2f50-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a2f50-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a2f50-112">En matris med index `idx` som `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="a2f50-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>