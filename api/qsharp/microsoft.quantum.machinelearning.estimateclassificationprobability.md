---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: EstimateClassificationProbability-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725959"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="0025d-102">EstimateClassificationProbability-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0025d-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="0025d-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0025d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0025d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0025d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0025d-105">Med ett exempel och en sekventiell klassificerare beräknar klassificerings sannolikheten för det exemplet genom att upprepade gånger mäta utdata från klassificeraren i det angivna exemplet.</span><span class="sxs-lookup"><span data-stu-id="0025d-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="0025d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0025d-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="0025d-107">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0025d-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0025d-108">Toleransen för att tillåta kodning av exemplet i en tillstånds förberedelse åtgärd.</span><span class="sxs-lookup"><span data-stu-id="0025d-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="0025d-109">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="0025d-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="0025d-110">Den sekventiella modell som används för att beräkna klassificerings sannolikheten för det aktuella exemplet.</span><span class="sxs-lookup"><span data-stu-id="0025d-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="0025d-111">exempel: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0025d-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0025d-112">Funktions vektorn för det exempel som ska klassificeras.</span><span class="sxs-lookup"><span data-stu-id="0025d-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="0025d-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0025d-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0025d-114">Antalet mätningar som ska användas vid uppskattning av klassificerings sannolikheten.</span><span class="sxs-lookup"><span data-stu-id="0025d-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="0025d-115">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0025d-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0025d-116">En uppskattning av klassificerings sannolikheten för det aktuella exemplet.</span><span class="sxs-lookup"><span data-stu-id="0025d-116">An estimate of the classification probability for the given sample.</span></span>