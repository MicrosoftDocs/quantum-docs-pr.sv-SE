---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: Funktionen TrotterStep
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 4c0e7dd89b1beae9fb6a35ae5b8d16e09d355ab8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854710"
---
# <a name="trotterstep-function"></a>Funktionen TrotterStep

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementerar en enda tids period – steg-för-steg-utveckling enligt systemet som beskrivs i `EvolutionGenerator` använda en Trotter – Suzuki-dekomposition.

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

En fullständig beskrivning av systemet som ska simuleras.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Ordning för Trotter Integrator. Det måste vara antingen 1 eller ett jämnt tal.


### <a name="trotterstepsize--double"></a>trotterStepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)

Varaktighet för simulerad tids utveckling i ett enda Trotter-steg.



## <a name="output--qubit--unit--is-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

Enhetlig drift som uppskattar ett enda steg i tids utvecklingen för varaktighet `trotterStepSize` .

## <a name="remarks"></a>Kommentarer

Mer information om Trotter – Suzuki diskomposition finns i [Tidssorterad sammansättning](/quantum/libraries/control-flow#time-ordered-composition).