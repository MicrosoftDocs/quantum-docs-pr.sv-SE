---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: ApplyAmplitudeAmplification-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: be884eab70c7f72f994baf6bd7caf05769e0d5f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732035"
---
# <a name="applyamplitudeamplification-operation"></a><span data-ttu-id="0474a-102">ApplyAmplitudeAmplification-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0474a-102">ApplyAmplitudeAmplification operation</span></span>

<span data-ttu-id="0474a-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="0474a-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="0474a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0474a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0474a-105">Använder amplitud-förstärkning för ett angivet register med en angiven uppsättning faser och Oracle för att avspegla de ursprungliga och slutliga tillstånden.</span><span class="sxs-lookup"><span data-stu-id="0474a-105">Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.</span></span>

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0474a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0474a-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="0474a-107">faser: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="0474a-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="0474a-108">En uppsättning faser som beskriver de partiella speglingarna i varje steg i algoritmen för amplitud förstärkning.</span><span class="sxs-lookup"><span data-stu-id="0474a-108">A set of phases describing the partial reflections at each step of the amplitude amplification algorithm.</span></span> <span data-ttu-id="0474a-109">Se @"microsoft.quantum.amplitudeamplification.standardreflectionphases" ett exempel.</span><span class="sxs-lookup"><span data-stu-id="0474a-109">See @"microsoft.quantum.amplitudeamplification.standardreflectionphases" for an example.</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="0474a-110">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="0474a-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="0474a-111">En Oracle som visar om det ursprungliga läget.</span><span class="sxs-lookup"><span data-stu-id="0474a-111">An oracle that reflects about the initial state.</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="0474a-112">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="0474a-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="0474a-113">En Oracle som återspeglar det önskade slutliga läget.</span><span class="sxs-lookup"><span data-stu-id="0474a-113">An oracle that reflects about the desired final state.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0474a-114">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0474a-114">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0474a-115">Ett register för att utföra amplitud förstärkning på.</span><span class="sxs-lookup"><span data-stu-id="0474a-115">A register to perform amplitude amplification on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0474a-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0474a-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

