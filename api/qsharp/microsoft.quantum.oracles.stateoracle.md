---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 005d7862214abb3dcb9c0caa006343720d179a52
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854472"
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