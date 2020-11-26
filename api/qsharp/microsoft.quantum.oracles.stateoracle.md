---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6b2cf09c23942a586414daccb99cbb27b5026b9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226612"
---
# <a name="stateoracle-user-defined-type"></a>StateOracle-användardefinierad typ

Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representerar en Oracle för tillstånds förberedelse.

Indata till Oracle-$O $ är:

- Ett heltal som indexerar flaggan qubit $f $.
- Systemet registrerar $s $ som kommer att lagra det önskade Quantum-läget $ \ket{\psi} \_ s $.

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Kommentarer

Den här Oracle definieras av $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ PSI} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ agerar på beräknings bas status $ \ket {0} \_ {f} \ket {0} \_ s $ för att skapa mål tillstånd $ \ket{\psi} \_ s $ med amplitud $ \lambda $ för att skapa mål tillstånd $ \ket s $ med amplitud $ $ i den bas {1} \_ som
Den första parametern är ett index för qubit-registret för $ \ket {0} \_ f $. Den andra parametern omfattar båda registren.