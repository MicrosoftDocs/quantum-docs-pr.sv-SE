---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: Funktionen ObliviousOracleFromDeterministicStateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 9e18776ad4d6adf0068213117c6d1d8ed5c5f126
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732203"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a>Funktionen ObliviousOracleFromDeterministicStateOracle

Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paketfilerna [](https://nuget.org/packages/)


Kombinerar Oracle- `DeterministicStateOracle` och `ObliviousOracle` .

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a>Indata

### <a name="ancillaoracle--deterministicstateoracle"></a>ancillaOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

En tillstånds förberedelse Oracle $A $ av typ som `DeterministicStateOracle` agerar på registrera $a $.


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

En Oracle $U $ av typ som `ObliviousOracle` agerar gemensamt på registrera $a, s $.



## <a name="output--obliviousoracle"></a>Utdata: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

En Oracle $O = UA $ av typen `ObliviousOracle` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. Quantum. Oracles. ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)