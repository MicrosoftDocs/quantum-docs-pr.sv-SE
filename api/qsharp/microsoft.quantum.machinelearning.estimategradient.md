---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: f42cc30c98346a25f584d7527227a95cb413c32b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730750"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="2125a-102">EstimateGradient-åtgärd</span><span class="sxs-lookup"><span data-stu-id="2125a-102">EstimateGradient operation</span></span>

<span data-ttu-id="2125a-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2125a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2125a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2125a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2125a-105">Uppskattar inlärnings toningen för en sekventiell klassificerare i en viss modell och för en viss kodad indatamängd.</span><span class="sxs-lookup"><span data-stu-id="2125a-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="2125a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2125a-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="2125a-107">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="2125a-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="2125a-108">Den sekventiella modell vars toning ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="2125a-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="2125a-109">encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="2125a-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="2125a-110">En inläsning till den sekventiella klassificeraren, kodad i en tillstånds förberedelse åtgärd.</span><span class="sxs-lookup"><span data-stu-id="2125a-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="2125a-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2125a-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2125a-112">Antalet mått som ska användas för att uppskatta övertoningen.</span><span class="sxs-lookup"><span data-stu-id="2125a-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="2125a-113">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2125a-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2125a-114">En uppskattning av inlärnings toningen vid angivna ingångs-och modell parametrar.</span><span class="sxs-lookup"><span data-stu-id="2125a-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="2125a-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="2125a-115">Remarks</span></span>

<span data-ttu-id="2125a-116">Den här åtgärden använder ett Hadamard-test och parameter Shift-tekniken tillsammans för att beräkna övertoningen.</span><span class="sxs-lookup"><span data-stu-id="2125a-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>