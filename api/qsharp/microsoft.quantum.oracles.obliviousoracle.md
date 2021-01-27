---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 793e72af56e288f9b437302f9958665e92e5e763
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842551"
---
# <a name="obliviousoracle-user-defined-type"></a>ObliviousOracle-användardefinierad typ

Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representerar en Oblivious amplitud-förstärkning för Oracle.

Indata till Oracle-$O $ är:

- Ancilla registrera $a $ som $O $ agerar på.
- Systemet registrerar $s $ som du vill att den önskade enhetliga $U $ ska tillämpas på, efter att du har valt att registrera $a $ i tillstånd $ \ket{t} \_ a $.

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Kommentarer

Den här Oracle definieras av $ $ O\ket {s} \_ a\ket {\ PSI} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ agerar i Ancilla State $ \ket{s} \_ a $ för att implementera den enhetliga $U $ i alla system tillstånd $ \ket{\psi} \_ s $ med amplitud $ \lambda $ i det här avsnittet som flaggats av $ \ket{t} \_ a $.
Den första parametern är qubit-registret för $ \ket{s} \_ a $. Den andra parametern är qubit-registret för $ \ket{\psi} \_ s $.