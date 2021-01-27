---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: TimeDependentSimulationAlgorithm-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: 4f393c958e686f2ded3bf3372ff9fd52b2a363cd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854125"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a>TimeDependentSimulationAlgorithm-användardefinierad typ

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representerar en tids beroende simulerings algoritm.

En tids beroende simulerings teknik konverterar en <xref:microsoft.quantum.simulation.evolutionschedule>
till en enhetlig tids utveckling under en viss tids period.

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

