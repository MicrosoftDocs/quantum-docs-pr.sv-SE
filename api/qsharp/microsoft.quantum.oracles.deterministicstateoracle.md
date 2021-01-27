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
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="470fa-102">DeterministicStateOracle-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="470fa-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="470fa-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="470fa-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="470fa-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="470fa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="470fa-105">Representerar en Oracle för att förbereda deterministiska tillstånd.</span><span class="sxs-lookup"><span data-stu-id="470fa-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="470fa-106">Indatamängden till Oracle-$O $ är:</span><span class="sxs-lookup"><span data-stu-id="470fa-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="470fa-107">Registret som kommer att lagra det önskade Quantum-läget $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="470fa-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="470fa-108">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="470fa-108">Remarks</span></span>

<span data-ttu-id="470fa-109">Den här Oracle definieras av $O \ket {0} = \ket{\psi} $ reagerar på beräknings bas tillstånd $ \ket {0} $ för att skapa tillstånd $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="470fa-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="470fa-110">Den första parametern är qubit-registret för $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="470fa-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>