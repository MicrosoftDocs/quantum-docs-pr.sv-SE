---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Exempel funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: ddff72bbed6f20e8e0ceb3bfe3fc50a3da0bd2a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211635"
---
# <a name="sampled-function"></a><span data-ttu-id="70560-102">Exempel funktion</span><span class="sxs-lookup"><span data-stu-id="70560-102">Sampled function</span></span>

<span data-ttu-id="70560-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="70560-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="70560-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="70560-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="70560-105">Exempel på en specifik matris med det aktuella schemat.</span><span class="sxs-lookup"><span data-stu-id="70560-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="70560-106">Indata</span><span class="sxs-lookup"><span data-stu-id="70560-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="70560-107">schema: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="70560-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="70560-108">Ett schema som ska användas i samplings värden.</span><span class="sxs-lookup"><span data-stu-id="70560-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="70560-109">värden: ' inte []</span><span class="sxs-lookup"><span data-stu-id="70560-109">values : 'T[]</span></span>

<span data-ttu-id="70560-110">En matris med värden som ska samplas.</span><span class="sxs-lookup"><span data-stu-id="70560-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="70560-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="70560-111">Output : 'T[]</span></span>

<span data-ttu-id="70560-112">En matris med element från värden, efter det aktuella schemat.</span><span class="sxs-lookup"><span data-stu-id="70560-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="70560-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="70560-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="70560-114">Inte</span><span class="sxs-lookup"><span data-stu-id="70560-114">'T</span></span>

