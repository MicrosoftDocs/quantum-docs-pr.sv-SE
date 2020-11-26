---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: Funktionen InterpolateGeneratorSystems
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: ee47637996313fe1b77c76f00b08417dac956247
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230590"
---
# <a name="interpolategeneratorsystems-function"></a><span data-ttu-id="70efd-102">Funktionen InterpolateGeneratorSystems</span><span class="sxs-lookup"><span data-stu-id="70efd-102">InterpolateGeneratorSystems function</span></span>

<span data-ttu-id="70efd-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="70efd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="70efd-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="70efd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="70efd-105">Returnerar en `TimeDependentGeneratorSystem` som representerar den linjära interpolering mellan två `GeneratorSystem` s.</span><span class="sxs-lookup"><span data-stu-id="70efd-105">Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.</span></span>

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="70efd-106">Indata</span><span class="sxs-lookup"><span data-stu-id="70efd-106">Input</span></span>

### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="70efd-107">generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="70efd-107">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="70efd-108">Start `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="70efd-108">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="70efd-109">generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="70efd-109">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="70efd-110">Slutet `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="70efd-110">The end `GeneratorSystem`.</span></span>



## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="70efd-111">Utdata: [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="70efd-111">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="70efd-112">Ett `TimeDependentGeneratorSystem` som representerar ett system som är summan av data Generator systemen, med en vikt på $ (1-s) $ på `generatorSystemStart` och vikt $s $ på `generatorSystemEnd` .</span><span class="sxs-lookup"><span data-stu-id="70efd-112">A `TimeDependentGeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="70efd-113">Se även</span><span class="sxs-lookup"><span data-stu-id="70efd-113">See Also</span></span>

- [<span data-ttu-id="70efd-114">Microsoft. Quantum. simulering. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="70efd-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [<span data-ttu-id="70efd-115">Microsoft. Quantum. simulering. TimeDependentGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="70efd-115">Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)