---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Exempel funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732318"
---
# <a name="sampled-function"></a><span data-ttu-id="74164-102">Exempel funktion</span><span class="sxs-lookup"><span data-stu-id="74164-102">Sampled function</span></span>

<span data-ttu-id="74164-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="74164-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="74164-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="74164-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="74164-105">Exempel på en specifik matris med det aktuella schemat.</span><span class="sxs-lookup"><span data-stu-id="74164-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="74164-106">Indata</span><span class="sxs-lookup"><span data-stu-id="74164-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="74164-107">schema: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="74164-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="74164-108">Ett schema som ska användas i samplings värden.</span><span class="sxs-lookup"><span data-stu-id="74164-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="74164-109">värden: ' inte []</span><span class="sxs-lookup"><span data-stu-id="74164-109">values : 'T[]</span></span>

<span data-ttu-id="74164-110">En matris med värden som ska samplas.</span><span class="sxs-lookup"><span data-stu-id="74164-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="74164-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="74164-111">Output : 'T[]</span></span>

<span data-ttu-id="74164-112">En matris med element från värden, efter det aktuella schemat.</span><span class="sxs-lookup"><span data-stu-id="74164-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="74164-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="74164-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="74164-114">Inte</span><span class="sxs-lookup"><span data-stu-id="74164-114">'T</span></span>

