---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 10ae9e52f298cdfb92dd6a9e5cf85960bece6800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842597"
---
# <a name="deterministicstateoracle-user-defined-type"></a>DeterministicStateOracle-användardefinierad typ

Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representerar en Oracle för att förbereda deterministiska tillstånd.

Indatamängden till Oracle-$O $ är:

- Registret som kommer att lagra det önskade Quantum-läget $ \ket{\psi} \_ s $.

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Kommentarer

Den här Oracle definieras av $O \ket {0} = \ket{\psi} $ reagerar på beräknings bas tillstånd $ \ket {0} $ för att skapa tillstånd $ \ket{\psi} $.
Den första parametern är qubit-registret för $ \ket{\psi} $.