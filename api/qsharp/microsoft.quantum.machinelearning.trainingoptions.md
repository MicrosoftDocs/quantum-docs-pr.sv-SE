---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: TrainingOptions-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 5ecc2b5175a4e8db78f72311ac1d5ff964bae811
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732291"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="9f565-102">TrainingOptions-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="9f565-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="9f565-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9f565-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="9f565-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9f565-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9f565-105">En samling alternativ som ska användas i träna Quantum-klassificerare.</span><span class="sxs-lookup"><span data-stu-id="9f565-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="9f565-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="9f565-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="9f565-107">Learningrate ligger: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9f565-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9f565-108">Den inlärnings takt med vilken övertoningar ska skalas om när modell parametrar uppdateras under inlärnings steg.</span><span class="sxs-lookup"><span data-stu-id="9f565-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="9f565-109">Tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9f565-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9f565-110">Den ungefärliga tolerans som ska användas när du förbereder exempel i Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="9f565-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="9f565-111">MinibatchSize: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f565-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f565-112">Antalet prover som ska användas i varje minibatch för utbildning.</span><span class="sxs-lookup"><span data-stu-id="9f565-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="9f565-113">NMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f565-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f565-114">Antalet gånger för att mäta varje klassificerings resultat för att uppskatta sannolikheten för klassificering.</span><span class="sxs-lookup"><span data-stu-id="9f565-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="9f565-115">MaxEpochs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f565-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f565-116">Det maximala antalet epoker för att träna varje modell för.</span><span class="sxs-lookup"><span data-stu-id="9f565-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="9f565-117">MaxStalls: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f565-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f565-118">Det maximala antalet gånger som en utbildnings värde är tillåten till bås (ungefär noll toning) innan det går.</span><span class="sxs-lookup"><span data-stu-id="9f565-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="9f565-119">StochasticRescaleFactor: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9f565-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9f565-120">Mängden stoppade stoppade modeller innan en uppdatering görs igen.</span><span class="sxs-lookup"><span data-stu-id="9f565-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="9f565-121">ScoringPeriod: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f565-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f565-122">Det antal tonings steg som ska tas mellan Poäng poängen.</span><span class="sxs-lookup"><span data-stu-id="9f565-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="9f565-123">För bästa precision anger du 1.</span><span class="sxs-lookup"><span data-stu-id="9f565-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="9f565-124">VerboseMessage: [sträng](xref:microsoft.quantum.lang-ref.string) -> [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9f565-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="9f565-125">En funktion som kan användas för att ge utförlig feedback.</span><span class="sxs-lookup"><span data-stu-id="9f565-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="9f565-126">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="9f565-126">Remarks</span></span>

<span data-ttu-id="9f565-127">Denna UDT ska inte skapas direkt, utan bör istället anges genom @"microsoft.quantum.machinelearning.defaulttrainingoptions" att anropa och sedan använda `w/` operatorn för att åsidosätta olika standardvärden.</span><span class="sxs-lookup"><span data-stu-id="9f565-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="9f565-128">Om du till exempel vill använda 100 000-mått och högst 8 utbildnings epoker:</span><span class="sxs-lookup"><span data-stu-id="9f565-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="9f565-129">Referenser</span><span class="sxs-lookup"><span data-stu-id="9f565-129">References</span></span>

- [<span data-ttu-id="9f565-130">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="9f565-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)