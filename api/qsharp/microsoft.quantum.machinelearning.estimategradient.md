---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 79f4abdf131509d4948a3c114e631118329f88d8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211856"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="17e6b-102">EstimateGradient-åtgärd</span><span class="sxs-lookup"><span data-stu-id="17e6b-102">EstimateGradient operation</span></span>

<span data-ttu-id="17e6b-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="17e6b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="17e6b-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="17e6b-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="17e6b-105">Uppskattar inlärnings toningen för en sekventiell klassificerare i en viss modell och för en viss kodad indatamängd.</span><span class="sxs-lookup"><span data-stu-id="17e6b-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="17e6b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="17e6b-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="17e6b-107">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="17e6b-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="17e6b-108">Den sekventiella modell vars toning ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="17e6b-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="17e6b-109">encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="17e6b-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="17e6b-110">En inläsning till den sekventiella klassificeraren, kodad i en tillstånds förberedelse åtgärd.</span><span class="sxs-lookup"><span data-stu-id="17e6b-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="17e6b-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="17e6b-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="17e6b-112">Antalet mått som ska användas för att uppskatta övertoningen.</span><span class="sxs-lookup"><span data-stu-id="17e6b-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="17e6b-113">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="17e6b-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="17e6b-114">En uppskattning av inlärnings toningen vid angivna ingångs-och modell parametrar.</span><span class="sxs-lookup"><span data-stu-id="17e6b-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="17e6b-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="17e6b-115">Remarks</span></span>

<span data-ttu-id="17e6b-116">Den här åtgärden använder ett Hadamard-test och parameter Shift-tekniken tillsammans för att beräkna övertoningen.</span><span class="sxs-lookup"><span data-stu-id="17e6b-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>