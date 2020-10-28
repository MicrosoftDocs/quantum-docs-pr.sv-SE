---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: Funktionen PauliEvolutionSet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 89c81aca4cfad6087d764ac8f5a0f1426e905e4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732102"
---
# <a name="paulievolutionset-function"></a>Funktionen PauliEvolutionSet

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paketfilerna [](https://nuget.org/packages/)


Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i Pauli-basen.

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>Utdata: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

En `EvolutionSet` som mappar en `GeneratorIndex` för Pauli-basen till en EvolutionUnitary.

## <a name="remarks"></a>Kommentarer

Detta erhålls genom en partiell tillämpning av <xref:microsoft.quantum.simulation.paulievolutionfunction> .