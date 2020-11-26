---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: Funktionen IdentityGeneratorIndex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 2dd3c705b0496df1719dc677e4defea5e435b839
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229298"
---
# <a name="identitygeneratorindex-function"></a>Funktionen IdentityGeneratorIndex

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar ett Generator index som är konsekvent med noll-Hamiltonian, `H = 0` som motsvarar Identity Evolutionary-åtgärden.

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Indata

### <a name="idxterm--int"></a>idxTerm: [int](xref:microsoft.quantum.lang-ref.int)

Den här indatan ignoreras och definieras för konsekvens med den <xref:microsoft.quantum.simulation.generatorsystem> användardefinierade typen.



## <a name="output--generatorindex"></a>Utdata: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Ett Generator index som representerar utvecklingen under Hamiltonian-$H = $0.