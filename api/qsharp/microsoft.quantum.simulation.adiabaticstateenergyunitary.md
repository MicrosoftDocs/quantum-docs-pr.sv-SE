---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: AdiabaticStateEnergyUnitary-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 642f6a0af76b3b2d0703f0377c379abf33ecee71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732515"
---
# <a name="adiabaticstateenergyunitary-operation"></a>AdiabaticStateEnergyUnitary-åtgärd

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paketfilerna [](https://nuget.org/packages/)


Utför tillstånds förberedelse genom att använda en `statePrepUnitary` på ingångs läget, följt av adiabatic-tillstånds förberedelse med hjälp av en `adiabaticUnitary` , och slutligen en uppskattning av fasen med avseende `qpeUnitary` på det resulterande läget med hjälp av en `phaseEstAlgorithm` .

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a>Indata

### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En Oracle som representerar tillstånds förberedelse för den inledande dynamiska generatorn.


### <a name="adiabaticunitary--qubit--unit"></a>adiabaticUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En Oracle som representerar algoritmen för adiabatic-utveckling som används för att implementera svepen till det slutliga tillståndets slut.


### <a name="qpeunitary--qubit--unit-adj--ctl"></a>qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL

En Oracle som representerar en enhetlig operatör $U $ som representerar utvecklingen för tid $ \delta t $ under en dynamisk Generator med jord tillstånd $ \ket{\phi} $ och mark State Energy $E = \phi \\ , \delta t $.


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [dubbel](xref:microsoft.quantum.lang-ref.double) 

En åtgärd som utför en fas uppskattning för en bestämd åtgärd.
Se [uppskattning av iterativa faser](/quantum/libraries/characterization#iterative-phase-estimation) för mer information.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ett register över qubits som ska användas för att utföra simuleringen.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)

En uppskattning av $ \hat{\phi} $ av mark State Energy $ \phi $ av generatorn som representeras av $U $.