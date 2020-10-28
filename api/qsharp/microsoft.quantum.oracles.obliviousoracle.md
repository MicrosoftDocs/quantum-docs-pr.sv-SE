---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 7c5b35984f3c8828a5ba9bdae8f9effbc1d378f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726481"
---
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="0025f-102">ObliviousOracle-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="0025f-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="0025f-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="0025f-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="0025f-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0025f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0025f-105">Representerar en Oblivious amplitud-förstärkning för Oracle.</span><span class="sxs-lookup"><span data-stu-id="0025f-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="0025f-106">Indata till Oracle-$O $ är:</span><span class="sxs-lookup"><span data-stu-id="0025f-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="0025f-107">Ancilla registrera $a $ som $O $ agerar på.</span><span class="sxs-lookup"><span data-stu-id="0025f-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="0025f-108">Systemet registrerar $s $ som du vill att den önskade enhetliga $U $ ska tillämpas på, efter att du har valt att registrera $a $ i tillstånd $ \ket{t} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="0025f-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="0025f-109">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="0025f-109">Remarks</span></span>

<span data-ttu-id="0025f-110">Den här Oracle definieras av $ $ O\ket {s} \_ a\ket {\ PSI} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ agerar i Ancilla State $ \ket{s} \_ a $ för att implementera den enhetliga $U $ i alla system tillstånd $ \ket{\psi} \_ s $ med amplitud $ \lambda $ i det här avsnittet som flaggats av $ \ket{t} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="0025f-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="0025f-111">Den första parametern är qubit-registret för $ \ket{s} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="0025f-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="0025f-112">Den andra parametern är qubit-registret för $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="0025f-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>