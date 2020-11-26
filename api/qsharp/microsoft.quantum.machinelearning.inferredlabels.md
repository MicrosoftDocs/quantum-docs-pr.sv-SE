---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: Funktionen InferredLabels
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196369"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="a61c1-102">Funktionen InferredLabels</span><span class="sxs-lookup"><span data-stu-id="a61c1-102">InferredLabels function</span></span>

<span data-ttu-id="a61c1-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a61c1-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a61c1-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a61c1-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a61c1-105">Med tanke på en klassificerings mat ris sannolikhet och en förskjutning, returnerar etiketten härledd från varje sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="a61c1-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="a61c1-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a61c1-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="a61c1-107">bias: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a61c1-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a61c1-108">Kompensationen mellan två klasser, vanligt vis resultatet av att träna en klassificerare.</span><span class="sxs-lookup"><span data-stu-id="a61c1-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="a61c1-109">sannolikhet: [dubbel](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a61c1-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a61c1-110">En matris med klassificerings sannolikheter för en uppsättning exempel, som vanligt vis resulterar i att klassificerings frekvensen uppskattas.</span><span class="sxs-lookup"><span data-stu-id="a61c1-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="a61c1-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a61c1-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a61c1-112">Etiketten härleds från varje klassificerings sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="a61c1-112">The label inferred from each classification probability.</span></span>