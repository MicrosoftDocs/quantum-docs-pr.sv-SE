---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: d04ee578c0e6f916e9a4da451075b79e0630c70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728173"
---
# <a name="robustphaseestimation-operation"></a>RobustPhaseEstimation-åtgärd

Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)

Paketfilerna [](https://nuget.org/packages/)


Utför den robusta uppskattnings algoritmen för en icke-iterativ Quantum-fas för en viss Oracle `U` -och eigenstate och ger en enda verklig uppskattning av fasen med avvikelse skalning vid Heisenberg-gränsen.

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Indata

### <a name="bitsprecision--int"></a>bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)

Detta ger en uppskattning av $ \phi $ med standard avvikelsen $ \sigma \le 2 \ Pi/2 ^ \text{bitsPrecision} $ med ett antal frågor som kan skalas, t. ex. $ \sigma \le 10,7 \pi/\text{antal frågor} $.


### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

En åtgärd som implementerar $U ^ m $ för angivet heltals-potenser $m $.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ett Quantum-register som $U $ reagerar på. Om den lagrar en eigenstate $ \ket{\phi} $ $U $ $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ för $ \phi\in (-\pi, \pi] $ en okänd fas.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Kommentarer

I gränsen för ett stort antal frågor Cramer-Rao nedre gränser för standard avvikelsen för uppskattningen av $ \phi $ som uppfyller $ \sigma \ge 2 \pi/\text{antal frågor} $.

## <a name="references"></a>Referenser

- Robust kalibrering av en universell Single-Qubit Gate-Set via robust fas uppskattning Shelby Kimmel, Guang lämnar demon Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677