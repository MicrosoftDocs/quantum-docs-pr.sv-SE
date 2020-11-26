---
uid: Microsoft.Quantum.Simulation.AddGeneratorSystems
title: Funktionen AddGeneratorSystems
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: d6e8f7085cf0558960d055dbeeb08740c3fab049
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229672"
---
# <a name="addgeneratorsystems-function"></a><span data-ttu-id="870ef-102">Funktionen AddGeneratorSystems</span><span class="sxs-lookup"><span data-stu-id="870ef-102">AddGeneratorSystems function</span></span>

<span data-ttu-id="870ef-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="870ef-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="870ef-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="870ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="870ef-105">Lägger till två `GeneratorSystem` s för att skapa en ny `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="870ef-105">Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.</span></span>

```qsharp
function AddGeneratorSystems (generatorSystemA : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemB : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="870ef-106">Indata</span><span class="sxs-lookup"><span data-stu-id="870ef-106">Input</span></span>

### <a name="generatorsystema--generatorsystem"></a><span data-ttu-id="870ef-107">generatorSystemA: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="870ef-107">generatorSystemA : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="870ef-108">Den första `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="870ef-108">The first `GeneratorSystem`.</span></span>


### <a name="generatorsystemb--generatorsystem"></a><span data-ttu-id="870ef-109">generatorSystemB: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="870ef-109">generatorSystemB : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="870ef-110">Den andra `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="870ef-110">The second `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="870ef-111">Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="870ef-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="870ef-112">Ett `GeneratorSystem` som representerar ett system som är summan av data Generator systemen.</span><span class="sxs-lookup"><span data-stu-id="870ef-112">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="870ef-113">Se även</span><span class="sxs-lookup"><span data-stu-id="870ef-113">See Also</span></span>

- [<span data-ttu-id="870ef-114">Microsoft. Quantum. simulering. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="870ef-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)