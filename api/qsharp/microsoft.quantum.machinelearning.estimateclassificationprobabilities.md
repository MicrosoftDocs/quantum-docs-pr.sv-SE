---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 1cd56f6a6483b00afb168f8d84301e73eae9af65
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211907"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="b4bfe-102">EstimateClassificationProbabilities-åtgärd</span><span class="sxs-lookup"><span data-stu-id="b4bfe-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="b4bfe-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b4bfe-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b4bfe-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b4bfe-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b4bfe-105">Med en uppsättning exempel och en sekventiell klassificerare beräknar klassificerings sannolikheten för dessa prover genom att upprepade gånger mäta utdata från klassificeraren i varje exempel.</span><span class="sxs-lookup"><span data-stu-id="b4bfe-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="b4bfe-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b4bfe-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="b4bfe-107">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b4bfe-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b4bfe-108">Toleransen för att tillåta kodning av exemplet i en tillstånds förberedelse åtgärd.</span><span class="sxs-lookup"><span data-stu-id="b4bfe-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="b4bfe-109">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="b4bfe-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="b4bfe-110">Den sekventiella modell som används för att uppskatta klassificerings sannolikheten för de aktuella exemplen.</span><span class="sxs-lookup"><span data-stu-id="b4bfe-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="b4bfe-111">exempel: [Double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="b4bfe-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="b4bfe-112">En matris med funktions vektorer för varje exempel som ska klassificeras.</span><span class="sxs-lookup"><span data-stu-id="b4bfe-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="b4bfe-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b4bfe-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b4bfe-114">Antalet mätningar som ska användas vid uppskattning av klassificerings sannolikheten.</span><span class="sxs-lookup"><span data-stu-id="b4bfe-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="b4bfe-115">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b4bfe-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b4bfe-116">En matris med uppskattningar av klassificerings sannolikheten för varje angivet exempel.</span><span class="sxs-lookup"><span data-stu-id="b4bfe-116">An array of estimates of the classification probability for each given sample.</span></span>