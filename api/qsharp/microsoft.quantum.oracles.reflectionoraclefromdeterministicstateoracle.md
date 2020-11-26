---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: Funktionen ReflectionOracleFromDeterministicStateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: 09de63d615a4d80e2b59deeddc07567aefe7660e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193836"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>Funktionen ReflectionOracleFromDeterministicStateOracle

Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Skapar reflektion om ett angivet tillstånd från en Oracle.

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a>Beskrivning

Med tanke på den deterministiska tillstånds förberedelse Oracle som representeras av en enhetlig matris $O $, är resultatet av den här funktionen en Oracle som tillämpar en reflektion runt det tillstånd $ \ket{\psi} $ som förbereds av Oracle $O $; det vill säga status $ \ket{\psi} $ som $O \ket {0} = \ket{\psi} $.

## <a name="input"></a>Indata

### <a name="oracle--deterministicstateoracle"></a>Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

En Oracle som förbereder kopior av status $ \ket{\psi} $.



## <a name="output--reflectionoracle"></a>Utdata: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

En Oracle som visar om tillstånd $ \ket{\psi} $.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. Quantum. Oracles. ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)