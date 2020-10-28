---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: Funktionen InterpolatedEvolution
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 18026b9872f6a3344a1e5c2122f55927975ccb59
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726307"
---
# <a name="interpolatedevolution-function"></a>Funktionen InterpolatedEvolution

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paketfilerna [](https://nuget.org/packages/)


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



## <a name="output--qubit--unit-adj--ctl"></a>Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL



## <a name="remarks"></a>Kommentarer

Om interpolsen har valts för att uppfylla adiabatic-villkoren returnerar den här funktionen en åtgärd som utför förberedelse av adiabatic-tillstånd för den slutliga dynamiska generatorn.