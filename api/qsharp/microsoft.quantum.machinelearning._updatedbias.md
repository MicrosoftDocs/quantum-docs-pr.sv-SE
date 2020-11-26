---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: _UpdatedBias funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 141edf6e425a060a995bfc181aefb1bcffdb128b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196709"
---
# <a name="_updatedbias-function"></a><span data-ttu-id="7cd90-102">_UpdatedBias funktion</span><span class="sxs-lookup"><span data-stu-id="7cd90-102">_UpdatedBias function</span></span>

<span data-ttu-id="7cd90-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7cd90-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7cd90-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7cd90-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="7cd90-105">Returnerar ett bias-värde som leder till närmaste lägsta värde för felklassificering.</span><span class="sxs-lookup"><span data-stu-id="7cd90-105">Returns a bias value that leads to near-minimum misclassification score.</span></span>

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a><span data-ttu-id="7cd90-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7cd90-106">Input</span></span>

### <a name="labeledprobabilities--doubleint"></a><span data-ttu-id="7cd90-107">labeledProbabilities: ([dubbel](xref:microsoft.quantum.lang-ref.double),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="7cd90-107">labeledProbabilities : ([Double](xref:microsoft.quantum.lang-ref.double),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>




### <a name="bias--double"></a><span data-ttu-id="7cd90-108">bias: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7cd90-108">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="tolerance--double"></a><span data-ttu-id="7cd90-109">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7cd90-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--double"></a><span data-ttu-id="7cd90-110">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7cd90-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

