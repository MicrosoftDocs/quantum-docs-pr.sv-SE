---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733339"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="0cf26-102">ReflectionOracle-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="0cf26-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="0cf26-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="0cf26-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="0cf26-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0cf26-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0cf26-105">Representerar en reflektions-Oracle.</span><span class="sxs-lookup"><span data-stu-id="0cf26-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="0cf26-106">En reflektions-Oracle, $O $, har indata:</span><span class="sxs-lookup"><span data-stu-id="0cf26-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="0cf26-107">Den fas $ \phi $ som det reflekterande del utrymmet ska roteras med.</span><span class="sxs-lookup"><span data-stu-id="0cf26-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="0cf26-108">Qubit-registret som den aktuella reflektionen ska utföras på.</span><span class="sxs-lookup"><span data-stu-id="0cf26-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="0cf26-109">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="0cf26-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a><span data-ttu-id="0cf26-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL</span><span class="sxs-lookup"><span data-stu-id="0cf26-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="0cf26-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="0cf26-111">Remarks</span></span>

<span data-ttu-id="0cf26-112">Den här Oracle $O = \boldone – (1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ utför en delvis reflektion av en fas $ \phi $ om ett enda rent tillstånd $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="0cf26-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>