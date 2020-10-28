---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: Funktionen SumGeneratorSystems
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: b667a6af313b5bb8950a34a6d0406976bde49311
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730691"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="9dd08-102">Funktionen SumGeneratorSystems</span><span class="sxs-lookup"><span data-stu-id="9dd08-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="9dd08-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9dd08-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9dd08-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9dd08-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9dd08-105">Lägger till flera `GeneratorSystem` s för att skapa en ny GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="9dd08-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="9dd08-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9dd08-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="9dd08-107">generatorSystems: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="9dd08-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="9dd08-108">En matris av typen `GeneratorSystem[]` .</span><span class="sxs-lookup"><span data-stu-id="9dd08-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="9dd08-109">Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="9dd08-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="9dd08-110">Ett `GeneratorSystem` som representerar ett system som är summan av data Generator systemen.</span><span class="sxs-lookup"><span data-stu-id="9dd08-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="9dd08-111">Se även</span><span class="sxs-lookup"><span data-stu-id="9dd08-111">See Also</span></span>

- [<span data-ttu-id="9dd08-112">Microsoft. Quantum. simulering. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="9dd08-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)