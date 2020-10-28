---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: Funktionen InterpolateGeneratorSystems
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: 9881c27577023dafff0bfc6d961877db44fec0eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726298"
---
# <a name="interpolategeneratorsystems-function"></a><span data-ttu-id="29511-102">Funktionen InterpolateGeneratorSystems</span><span class="sxs-lookup"><span data-stu-id="29511-102">InterpolateGeneratorSystems function</span></span>

<span data-ttu-id="29511-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="29511-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="29511-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29511-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="29511-105">Returnerar en `TimeDependentGeneratorSystem` som representerar den linjära interpolering mellan två `GeneratorSystem` s.</span><span class="sxs-lookup"><span data-stu-id="29511-105">Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.</span></span>

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="29511-106">Indata</span><span class="sxs-lookup"><span data-stu-id="29511-106">Input</span></span>

### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="29511-107">generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="29511-107">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="29511-108">Start `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="29511-108">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="29511-109">generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="29511-109">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="29511-110">Slutet `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="29511-110">The end `GeneratorSystem`.</span></span>



## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="29511-111">Utdata: [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="29511-111">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="29511-112">Ett `TimeDependentGeneratorSystem` som representerar ett system som är summan av data Generator systemen, med en vikt på $ (1-s) $ på `generatorSystemStart` och vikt $s $ på `generatorSystemEnd` .</span><span class="sxs-lookup"><span data-stu-id="29511-112">A `TimeDependentGeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="29511-113">Se även</span><span class="sxs-lookup"><span data-stu-id="29511-113">See Also</span></span>

- [<span data-ttu-id="29511-114">Microsoft. Quantum. simulering. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="29511-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [<span data-ttu-id="29511-115">Microsoft. Quantum. simulering. TimeDependentGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="29511-115">Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)