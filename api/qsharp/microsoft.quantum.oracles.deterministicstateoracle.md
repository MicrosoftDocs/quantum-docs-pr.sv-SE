---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6f8f80aacd3386ba61675101acb87e09fff5afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193938"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="d321b-102">DeterministicStateOracle-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="d321b-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="d321b-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="d321b-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="d321b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d321b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d321b-105">Representerar en Oracle för att förbereda deterministiska tillstånd.</span><span class="sxs-lookup"><span data-stu-id="d321b-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="d321b-106">Indatamängden till Oracle-$O $ är:</span><span class="sxs-lookup"><span data-stu-id="d321b-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="d321b-107">Registret som kommer att lagra det önskade Quantum-läget $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="d321b-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="d321b-108">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="d321b-108">Remarks</span></span>

<span data-ttu-id="d321b-109">Den här Oracle definieras av $O \ket {0} = \ket{\psi} $ reagerar på beräknings bas tillstånd $ \ket {0} $ för att skapa tillstånd $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="d321b-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="d321b-110">Den första parametern är qubit-registret för $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="d321b-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>