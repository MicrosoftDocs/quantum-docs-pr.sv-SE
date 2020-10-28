---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: Funktionen ScheduleLength
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: 77538984fbd7334712df423b991ef43ce31ed849
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732307"
---
# <a name="schedulelength-function"></a><span data-ttu-id="b956b-102">Funktionen ScheduleLength</span><span class="sxs-lookup"><span data-stu-id="b956b-102">ScheduleLength function</span></span>

<span data-ttu-id="b956b-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b956b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b956b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b956b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b956b-105">Returnerar antalet element i ett angivet samplings schema.</span><span class="sxs-lookup"><span data-stu-id="b956b-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="b956b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b956b-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="b956b-107">schema: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="b956b-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="b956b-108">Ett samplings schema vars längd ska returneras.</span><span class="sxs-lookup"><span data-stu-id="b956b-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="b956b-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b956b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b956b-110">Antalet element i angivet samplings schema.</span><span class="sxs-lookup"><span data-stu-id="b956b-110">The number of elements in the given sampling schedule.</span></span>