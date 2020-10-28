---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 65f4edcf2101190da0c6d00eb4dd21881143ceb0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733347"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="eb575-102">StateOracle-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="eb575-102">StateOracle user defined type</span></span>

<span data-ttu-id="eb575-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="eb575-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="eb575-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb575-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb575-105">Representerar en Oracle för tillstånds förberedelse.</span><span class="sxs-lookup"><span data-stu-id="eb575-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="eb575-106">Indata till Oracle-$O $ är:</span><span class="sxs-lookup"><span data-stu-id="eb575-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="eb575-107">Ett heltal som indexerar flaggan qubit $f $.</span><span class="sxs-lookup"><span data-stu-id="eb575-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="eb575-108">Systemet registrerar $s $ som kommer att lagra det önskade Quantum-läget $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="eb575-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="eb575-109">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="eb575-109">Remarks</span></span>

<span data-ttu-id="eb575-110">Den här Oracle definieras av $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ PSI} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ agerar på beräknings bas status $ \ket {0} \_ {f} \ket {0} \_ s $ för att skapa mål tillstånd $ \ket{\psi} \_ s $ med amplitud $ \lambda $ för att skapa mål tillstånd $ \ket s $ med amplitud $ $ i den bas {1} \_ som</span><span class="sxs-lookup"><span data-stu-id="eb575-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="eb575-111">Den första parametern är ett index för qubit-registret för $ \ket {0} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="eb575-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="eb575-112">Den andra parametern omfattar båda registren.</span><span class="sxs-lookup"><span data-stu-id="eb575-112">The second parameter encompassed both registers.</span></span>