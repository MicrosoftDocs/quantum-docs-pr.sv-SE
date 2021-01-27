---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: Funktionen InferredLabel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848424"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="9a2eb-102">Funktionen InferredLabel</span><span class="sxs-lookup"><span data-stu-id="9a2eb-102">InferredLabel function</span></span>

<span data-ttu-id="9a2eb-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9a2eb-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="9a2eb-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9a2eb-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="9a2eb-105">Med hänsyn till klassificerings sannolikhet och en förskjutning, returnerar etiketten härledd från den sannolikheten.</span><span class="sxs-lookup"><span data-stu-id="9a2eb-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="9a2eb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9a2eb-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="9a2eb-107">bias: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9a2eb-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9a2eb-108">Kompensationen mellan två klasser, vanligt vis resultatet av att träna en klassificerare.</span><span class="sxs-lookup"><span data-stu-id="9a2eb-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="9a2eb-109">sannolikhet: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9a2eb-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9a2eb-110">En klassificering som är sannolikhet för ett visst exempel, vilket vanligt vis uppstår vid uppskattning av klassificerings frekvensen.</span><span class="sxs-lookup"><span data-stu-id="9a2eb-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="9a2eb-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9a2eb-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9a2eb-112">Etiketten härleddes från den klassificerings sannolikheten.</span><span class="sxs-lookup"><span data-stu-id="9a2eb-112">The label inferred from the given classification probability.</span></span>