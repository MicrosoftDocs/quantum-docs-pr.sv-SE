---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: Funktionen StateOracleFromDeterministicStateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733342"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a>Funktionen StateOracleFromDeterministicStateOracle

Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paketfilerna [](https://nuget.org/packages/)


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