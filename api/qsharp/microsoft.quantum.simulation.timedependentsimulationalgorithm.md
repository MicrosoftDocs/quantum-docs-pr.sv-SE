---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: TimeDependentSimulationAlgorithm-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: 9d2a1a853005495b5a9df60ac1f0dcbfbdf7637f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734219"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="f5643-102">TimeDependentSimulationAlgorithm-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="f5643-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="f5643-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f5643-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f5643-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f5643-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f5643-105">Representerar en tids beroende simulerings algoritm.</span><span class="sxs-lookup"><span data-stu-id="f5643-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="f5643-106">En tids beroende simulerings teknik konverterar en <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="f5643-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="f5643-107">till en enhetlig tids utveckling under en viss tids period.</span><span class="sxs-lookup"><span data-stu-id="f5643-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

