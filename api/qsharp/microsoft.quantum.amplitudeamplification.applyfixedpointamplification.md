---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: f506be7b2e3f65cf89694e30d79c04ec30d25035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732022"
---
# <a name="applyfixedpointamplification-operation"></a>ApplyFixedPointAmplification-åtgärd

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paketfilerna [](https://nuget.org/packages/)


Algoritmen Fixed-Point Amplituds förstärkning

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a>Indata

### <a name="statepreporacle--stateoracle"></a>statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Enhetlig Oracle som förbereder start tillstånd.


### <a name="startqubits--qubit"></a>startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit-register



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

StartQubits måste ha statusen $ \ket{0 \cdots 0}. Den här åtgärden itererar över ett antal frågor i potenser på $2 $ tills ett maximalt antal frågor har nåtts eller mål status har hittats.