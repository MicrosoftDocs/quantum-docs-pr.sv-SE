---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: Funktionen InferredLabels
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848398"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="160f4-102">Funktionen InferredLabels</span><span class="sxs-lookup"><span data-stu-id="160f4-102">InferredLabels function</span></span>

<span data-ttu-id="160f4-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="160f4-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="160f4-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="160f4-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="160f4-105">Med tanke på en klassificerings mat ris sannolikhet och en förskjutning, returnerar etiketten härledd från varje sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="160f4-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="160f4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="160f4-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="160f4-107">bias: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="160f4-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="160f4-108">Kompensationen mellan två klasser, vanligt vis resultatet av att träna en klassificerare.</span><span class="sxs-lookup"><span data-stu-id="160f4-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="160f4-109">sannolikhet: [dubbel](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="160f4-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="160f4-110">En matris med klassificerings sannolikheter för en uppsättning exempel, som vanligt vis resulterar i att klassificerings frekvensen uppskattas.</span><span class="sxs-lookup"><span data-stu-id="160f4-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="160f4-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="160f4-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="160f4-112">Etiketten härleds från varje klassificerings sannolikhet.</span><span class="sxs-lookup"><span data-stu-id="160f4-112">The label inferred from each classification probability.</span></span>