---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: Funktionen DeterministicStateOracleFromStateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 539cc56e7ae4ead6654aaaae5353a771e06d2bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733363"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a>Funktionen DeterministicStateOracleFromStateOracle

Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paketfilerna [](https://nuget.org/packages/)


Konverterar en Oracle av typen `StateOracle` till `DeterministicStateOracle` .

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a>Indata

### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Indexet till flaggan qubit i `stateOracle` $A $, som uttryckligen agerar på två kassor: flaggan $f $ och system $s $, t. ex. $A \ket {0} \_ f\ket {\ PSI} \_ s $.


### <a name="stateoracle--stateoracle"></a>stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

En tillstånds förberedelse Oracle-$A $ av typen `StateOracle` .



## <a name="output--deterministicstateoracle"></a>Utdata: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Samma tillstånd som förbereder Oracle $A $, men nu av typ `DeterministicStateOracle` , så den agerar i ett register där $a, s $ inte längre uttryckligen separeras, t. ex.  $A \ket{0\psi} \_ {as} $.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Oracles. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)
- [Microsoft. Quantum. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)