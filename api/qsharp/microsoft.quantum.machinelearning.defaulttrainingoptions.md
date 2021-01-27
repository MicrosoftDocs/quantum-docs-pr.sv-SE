---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: Funktionen DefaultTrainingOptions
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855995"
---
# <a name="defaulttrainingoptions-function"></a><span data-ttu-id="97acd-102">Funktionen DefaultTrainingOptions</span><span class="sxs-lookup"><span data-stu-id="97acd-102">DefaultTrainingOptions function</span></span>

<span data-ttu-id="97acd-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="97acd-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="97acd-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="97acd-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="97acd-105">Returnerar en standard uppsättning med alternativ för utbildningar för utbildning.</span><span class="sxs-lookup"><span data-stu-id="97acd-105">Returns a default set of options for training classifiers.</span></span>

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a><span data-ttu-id="97acd-106">Utdata: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="97acd-106">Output : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="97acd-107">En rimlig uppsättning standard alternativ för utbildning som används vid utbildning av utbildning.</span><span class="sxs-lookup"><span data-stu-id="97acd-107">A reasonable set of default training options for use when training classifiers.</span></span>

## <a name="example"></a><span data-ttu-id="97acd-108">Exempel</span><span class="sxs-lookup"><span data-stu-id="97acd-108">Example</span></span>

<span data-ttu-id="97acd-109">Om du vill använda standard alternativen, men med ytterligare mått, använder du `w/` operatorn:</span><span class="sxs-lookup"><span data-stu-id="97acd-109">To use the default options, but with additional measurements, use the `w/` operator:</span></span>

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```