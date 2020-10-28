---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: f02267d48cf42fb5b02782dc6b667ac7b60a05dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733387"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="53619-102">DeterministicStateOracle-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="53619-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="53619-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="53619-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="53619-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53619-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53619-105">Representerar en Oracle för att förbereda deterministiska tillstånd.</span><span class="sxs-lookup"><span data-stu-id="53619-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="53619-106">Indatamängden till Oracle-$O $ är:</span><span class="sxs-lookup"><span data-stu-id="53619-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="53619-107">Registret som kommer att lagra det önskade Quantum-läget $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="53619-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="53619-108">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="53619-108">Remarks</span></span>

<span data-ttu-id="53619-109">Den här Oracle definieras av $O \ket {0} = \ket{\psi} $ reagerar på beräknings bas tillstånd $ \ket {0} $ för att skapa tillstånd $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="53619-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="53619-110">Den första parametern är qubit-registret för $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="53619-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>