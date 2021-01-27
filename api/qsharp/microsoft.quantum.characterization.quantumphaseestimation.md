---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 4bdf3de9dab20fa97ba47f15efec4b41a10709f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839664"
---
# <a name="quantumphaseestimation-operation"></a>QuantumPhaseEstimation-åtgärd

Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utför en skattning av Quantum-fasen för en specifik Oracle `U` och `targetState` läser fasen till en big-endian-register.

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

En åtgärd som implementerar $U ^ m $ för angivet heltals-potenser m.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ett Quantum-register som representerar det tillstånd $ \ket{\phi} $ som du har handlat om $U $. Om $ \ket{\phi} $ är en eigenstate av $U $, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ för $ \phi \in [0, 2 \ PI) $ en okänd fas.


### <a name="controlregister--bigendian"></a>controlRegister: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Ett heltals register med big-endian-representation som kan användas för att kontrol lera den angivna Oracle och som kommer att innehålla en representation av $ \phi $ efter den här åtgärdens användning. ControlRegister antas starta i det ursprungliga läget $ \ket{00\cdots 0} $, där register längden anger önskad precision.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

