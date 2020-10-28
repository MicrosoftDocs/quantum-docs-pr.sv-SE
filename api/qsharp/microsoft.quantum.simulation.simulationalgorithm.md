---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: SimulationAlgorithm-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: 9127a936bbf7a212e712645eabdf49fefc7a97d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734115"
---
# <a name="simulationalgorithm-user-defined-type"></a><span data-ttu-id="56239-102">SimulationAlgorithm-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="56239-102">SimulationAlgorithm user defined type</span></span>

<span data-ttu-id="56239-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="56239-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="56239-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="56239-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="56239-105">Representerar en tidshärledd simulerings-algoritm.</span><span class="sxs-lookup"><span data-stu-id="56239-105">Represents a time-independent simulation algorithm.</span></span>

<span data-ttu-id="56239-106">En tids oberoende simulerings teknik konverterar en <xref:microsoft.quantum.simulation.evolutiongenerator></span><span class="sxs-lookup"><span data-stu-id="56239-106">A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator></span></span>
<span data-ttu-id="56239-107">vid en viss tids utveckling under en viss tids period.</span><span class="sxs-lookup"><span data-stu-id="56239-107">to unitary time evolution for some time-interval.</span></span>

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```

