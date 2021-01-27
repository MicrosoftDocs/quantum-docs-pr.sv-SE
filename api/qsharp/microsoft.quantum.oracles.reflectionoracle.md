---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 1ef07126596b70d2c5574430656009116c34d2bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854494"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="48a72-102">ReflectionOracle-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="48a72-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="48a72-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="48a72-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="48a72-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48a72-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48a72-105">Representerar en reflektions-Oracle.</span><span class="sxs-lookup"><span data-stu-id="48a72-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="48a72-106">En reflektions-Oracle, $O $, har indata:</span><span class="sxs-lookup"><span data-stu-id="48a72-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="48a72-107">Den fas $ \phi $ som det reflekterande del utrymmet ska roteras med.</span><span class="sxs-lookup"><span data-stu-id="48a72-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="48a72-108">Qubit-registret som den aktuella reflektionen ska utföras på.</span><span class="sxs-lookup"><span data-stu-id="48a72-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="48a72-109">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="48a72-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a><span data-ttu-id="48a72-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="48a72-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="48a72-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="48a72-111">Remarks</span></span>

<span data-ttu-id="48a72-112">Den här Oracle $O = \boldone – (1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ utför en delvis reflektion av en fas $ \phi $ om ett enda rent tillstånd $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="48a72-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>