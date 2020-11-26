---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: Funktionen NMisclassifications
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196318"
---
# <a name="nmisclassifications-function"></a><span data-ttu-id="e0b3a-102">Funktionen NMisclassifications</span><span class="sxs-lookup"><span data-stu-id="e0b3a-102">NMisclassifications function</span></span>

<span data-ttu-id="e0b3a-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e0b3a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e0b3a-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e0b3a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="e0b3a-105">Med en uppsättning av uppskjutna etiketter och en uppsättning korrekta etiketter, returnerar antalet index där varje uppsättning etiketter skiljer sig.</span><span class="sxs-lookup"><span data-stu-id="e0b3a-105">Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.</span></span>

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a><span data-ttu-id="e0b3a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e0b3a-106">Input</span></span>

### <a name="proposed--int"></a><span data-ttu-id="e0b3a-107">Föreslagen: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e0b3a-107">proposed : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="actual--int"></a><span data-ttu-id="e0b3a-108">faktiskt: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e0b3a-108">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--int"></a><span data-ttu-id="e0b3a-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e0b3a-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e0b3a-110">Antalet index `idx` som `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="e0b3a-110">The number of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>