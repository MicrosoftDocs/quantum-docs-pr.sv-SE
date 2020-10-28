---
uid: Microsoft.Quantum.Research.Chemistry.JordanWignerOptimizedFermionEvolutionSet
title: Funktionen JordanWignerOptimizedFermionEvolutionSet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JordanWignerOptimizedFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: d2d916655b7538b39d5739d67dbb3fc9920cf67a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732155"
---
# <a name="jordanwigneroptimizedfermionevolutionset-function"></a>Funktionen JordanWignerOptimizedFermionEvolutionSet

Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)

Paketfilerna [](https://nuget.org/packages/)


Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i Pauli-basen.

```qsharp
function JordanWignerOptimizedFermionEvolutionSet (parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="input"></a>Indata

### <a name="parityqubit--qubit"></a>parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit som avgör tids utvecklingen.



## <a name="output--evolutionset"></a>Utdata: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

En `EvolutionSet` som mappar en `GeneratorIndex` för JWOptimized-basen till en EvolutionUnitary.