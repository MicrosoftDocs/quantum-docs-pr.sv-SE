---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: Funktionen PauliEvolutionSet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: fb53b90b6ab5ce1003f66b68a8c2ad8b3631f627
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230355"
---
# <a name="paulievolutionset-function"></a><span data-ttu-id="af98c-102">Funktionen PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="af98c-102">PauliEvolutionSet function</span></span>

<span data-ttu-id="af98c-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="af98c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="af98c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="af98c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="af98c-105">Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i Pauli-basen.</span><span class="sxs-lookup"><span data-stu-id="af98c-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="af98c-106">Utdata: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="af98c-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="af98c-107">En `EvolutionSet` som mappar en `GeneratorIndex` för Pauli-basen till en EvolutionUnitary.</span><span class="sxs-lookup"><span data-stu-id="af98c-107">An `EvolutionSet` that maps a `GeneratorIndex` for the Pauli basis to an \`EvolutionUnitary.</span></span>

## <a name="remarks"></a><span data-ttu-id="af98c-108">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="af98c-108">Remarks</span></span>

<span data-ttu-id="af98c-109">Detta erhålls genom en partiell tillämpning av <xref:microsoft.quantum.simulation.paulievolutionfunction> .</span><span class="sxs-lookup"><span data-stu-id="af98c-109">This is obtained by partial application of <xref:microsoft.quantum.simulation.paulievolutionfunction>.</span></span>