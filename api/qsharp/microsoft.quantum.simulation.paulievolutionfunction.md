---
uid: Microsoft.Quantum.Simulation.PauliEvolutionFunction
title: Funktionen PauliEvolutionFunction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 9b12dc4a05c99aad319799f8c6526cd3085e6dcd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847969"
---
# <a name="paulievolutionfunction-function"></a><span data-ttu-id="87f4a-102">Funktionen PauliEvolutionFunction</span><span class="sxs-lookup"><span data-stu-id="87f4a-102">PauliEvolutionFunction function</span></span>

<span data-ttu-id="87f4a-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="87f4a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="87f4a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="87f4a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="87f4a-105">Representerar en dynamisk generator som en uppsättning simulerade grindar och en expansion i Pauli-basen.</span><span class="sxs-lookup"><span data-stu-id="87f4a-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="87f4a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="87f4a-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="87f4a-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="87f4a-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="87f4a-108">Ett Generator index som återges som en enhetlig utveckling i Pauli-basen.</span><span class="sxs-lookup"><span data-stu-id="87f4a-108">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="87f4a-109">Utdata: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="87f4a-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="87f4a-110">En `EvolutionUnitary` som visar tids utveckling enligt termen som refereras i generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="87f4a-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>