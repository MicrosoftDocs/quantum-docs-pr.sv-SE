---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: Funktionen ScheduleLength
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: dd042b1282d2f5386ee0b67bf57ad4027eefd493
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854912"
---
# <a name="schedulelength-function"></a><span data-ttu-id="79e1b-102">Funktionen ScheduleLength</span><span class="sxs-lookup"><span data-stu-id="79e1b-102">ScheduleLength function</span></span>

<span data-ttu-id="79e1b-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="79e1b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="79e1b-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="79e1b-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="79e1b-105">Returnerar antalet element i ett angivet samplings schema.</span><span class="sxs-lookup"><span data-stu-id="79e1b-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="79e1b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="79e1b-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="79e1b-107">schema: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="79e1b-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="79e1b-108">Ett samplings schema vars längd ska returneras.</span><span class="sxs-lookup"><span data-stu-id="79e1b-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="79e1b-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="79e1b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="79e1b-110">Antalet element i angivet samplings schema.</span><span class="sxs-lookup"><span data-stu-id="79e1b-110">The number of elements in the given sampling schedule.</span></span>