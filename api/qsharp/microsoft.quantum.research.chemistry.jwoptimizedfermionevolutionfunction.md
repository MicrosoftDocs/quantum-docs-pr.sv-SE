---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: Funktionen JWOptimizedFermionEvolutionFunction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: d70bea8fcb5bd82ddad6dcd2b67c3eb178283bb3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857869"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a>Funktionen JWOptimizedFermionEvolutionFunction

Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)

Paket: [Microsoft. Quantum. Research. kemi](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i JWOptimized-basen.

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>Indata

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Ett Generator index som återges som en enhetlig utveckling i JWOptimized-basen.


### <a name="parityqubit--qubit"></a>parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit som avgör tids utvecklingen.



## <a name="output--evolutionunitary"></a>Utdata: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

En `EvolutionUnitary` som visar tids utveckling enligt termen som refereras i generatorIndex.