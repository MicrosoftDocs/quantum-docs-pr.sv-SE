---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: Funktionen PauliEvolutionSet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: fb53b90b6ab5ce1003f66b68a8c2ad8b3631f627
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230355"
---
# <a name="paulievolutionset-function"></a>Funktionen PauliEvolutionSet

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i Pauli-basen.

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>Utdata: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

En `EvolutionSet` som mappar en `GeneratorIndex` för Pauli-basen till en EvolutionUnitary.

## <a name="remarks"></a>Kommentarer

Detta erhålls genom en partiell tillämpning av <xref:microsoft.quantum.simulation.paulievolutionfunction> .