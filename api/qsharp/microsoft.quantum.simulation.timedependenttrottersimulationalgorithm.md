---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: Funktionen TimeDependentTrotterSimulationAlgorithm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: c827dd79af6f4b745adf8903ed2664d9e8255785
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858362"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a>Funktionen TimeDependentTrotterSimulationAlgorithm

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


`TimeDependentSimulationAlgorithm` funktion som använder en Trotter – Suzuki-dekomposition för att approximera en enhetlig operator som matchar tids beroende Schrodinger-ekvationen.

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a>Indata

### <a name="trotterstepsize--double"></a>trotterStepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)

Varaktighet för simulerad tids utveckling i ett enda Trotter-steg.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Ordning för Trotter Integrator. Det måste vara antingen 1 eller ett jämnt tal.



## <a name="output--timedependentsimulationalgorithm"></a>Utdata: [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)

En `TimeDependentSimulationAlgorithm` typ.