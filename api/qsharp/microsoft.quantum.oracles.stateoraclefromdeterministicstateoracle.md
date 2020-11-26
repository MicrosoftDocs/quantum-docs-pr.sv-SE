---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: Funktionen StateOracleFromDeterministicStateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: f3c225ee185b4b70ab0ea60af6f0fb154288d9bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193819"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a>Funktionen StateOracleFromDeterministicStateOracle

Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konverterar en Oracle av typen `DeterministicStateOracle` till `StateOracle` .

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a>Indata

### <a name="deterministicstateoracle--deterministicstateoracle"></a>deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

En tillstånds förberedelse Oracle-$A $ av typen `DeterministicStateOracle` .



## <a name="output--stateoracle"></a>Utdata: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Samma tillstånd som förbereder Oracle $A $, men nu av typen `StateOracle` . Observera att flagg indexet i det här `StateOracle` är en dummy-variabel och har ingen påverkan.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. Quantum. Oracles. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)