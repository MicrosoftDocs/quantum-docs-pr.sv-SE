---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 8d36f74fbf122469e9e829b950e4ed9a6e3a35a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733163"
---
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="f6265-102">GeneratorIndex-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="f6265-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="f6265-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f6265-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f6265-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6265-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6265-105">Representerar en enda primitiv term i uppsättningen med alla dynamiska generatorer, t. ex. Hermitian-operatörer, för vilka det finns en karta från den generatorn till tids utveckling av generatorn `EvolutionSet` .</span><span class="sxs-lookup"><span data-stu-id="f6265-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="f6265-106">Det första elementet (int [], Double []) är index som en term, men Pauli-strängen XXY med koefficient 0,5 skulle indexeras av ([1, 1, 2], [0,5]).</span><span class="sxs-lookup"><span data-stu-id="f6265-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="f6265-107">Alternativt kan Hamiltonians parameterstyrda av en kontinuerlig variabel, till exempel X cos φ + Y sin φ, representeras av ([], [φ]).</span><span class="sxs-lookup"><span data-stu-id="f6265-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="f6265-108">Det andra elementet indexerar under systemet som generatorn agerar på.</span><span class="sxs-lookup"><span data-stu-id="f6265-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a><span data-ttu-id="f6265-109">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="f6265-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="f6265-110">Tolkningen av en `GeneratorIndex` har inte definierats, förutom med referens till en viss uppsättning generatorer.</span><span class="sxs-lookup"><span data-stu-id="f6265-110">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6265-111">Se även</span><span class="sxs-lookup"><span data-stu-id="f6265-111">See Also</span></span>

- [<span data-ttu-id="f6265-112">Microsoft. Quantum. simulering. EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="f6265-112">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="f6265-113">Microsoft. Quantum. simulering. PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="f6265-113">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)