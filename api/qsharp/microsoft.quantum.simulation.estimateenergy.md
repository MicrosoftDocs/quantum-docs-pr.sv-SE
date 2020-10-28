---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: EstimateEnergy-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: ba4a5372aaf092c3ac3a1302f9715ca643be8436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732107"
---
# <a name="estimateenergy-operation"></a>EstimateEnergy-åtgärd

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paketfilerna [](https://nuget.org/packages/)


Utför tillstånds förberedelse genom att använda en `statePrepUnitary` på en automatiskt tilldelad beräkning av indatatypen med avseende `qpeUnitary` på det resulterande läget med hjälp av en `phaseEstAlgorithm` .

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a>Indata

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som används för att utföra simuleringen.


### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En Oracle som representerar tillstånds förberedelse för den inledande dynamiska generatorn.


### <a name="qpeunitary--qubit--unit-adj--ctl"></a>qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL

En Oracle som representerar en enhetlig operatör $U $ som representerar utvecklingen för tid $ \delta t $ under en dynamisk Generator med jord tillstånd $ \ket{\phi} $ och mark State Energy $E = \phi \\ , \delta t $.


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [dubbel](xref:microsoft.quantum.lang-ref.double) 

En åtgärd som utför en fas uppskattning för en bestämd åtgärd.
Se [uppskattning av iterativa faser](/quantum/libraries/characterization#iterative-phase-estimation) för mer information.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)

En uppskattning av $ \hat{\phi} $ av mark State Energy $ \phi $ av den kraftiga energin för generatorn som representeras av $U $.