---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: Funktionen InterpolatedEvolution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 4d2e04513c96c6e5f41e85f1df685e91e2973098
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858096"
---
# <a name="interpolatedevolution-function"></a>Funktionen InterpolatedEvolution

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Interpolerar mellan två generatorer med ett enhetligt schema och returnerar en åtgärd som tillämpar simulerad utveckling under den resulterande tids beroende generatorn för en qubit-registrering.

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="interpolationtime--double"></a>interpolationTime: [dubbel](xref:microsoft.quantum.lang-ref.double)

Tid för att utföra interpolation över.


### <a name="evolutiongeneratorstart--evolutiongenerator"></a>evolutionGeneratorStart: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Första generatorn för att simulera utvecklingen under.


### <a name="evolutiongeneratorend--evolutiongenerator"></a>evolutionGeneratorEnd: [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Slutlig generator för att simulera utveckling under.


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a>timeDependentSimulationAlgorithm: [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)

En tids beroende simulerings algoritm som används för att simulera utvecklingen under det enhetliga sammanställnings schemat.



## <a name="output--qubit--unit--is-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL



## <a name="remarks"></a>Kommentarer

Om interpolsen har valts för att uppfylla adiabatic-villkoren returnerar den här funktionen en åtgärd som utför förberedelse av adiabatic-tillstånd för den slutliga dynamiska generatorn.