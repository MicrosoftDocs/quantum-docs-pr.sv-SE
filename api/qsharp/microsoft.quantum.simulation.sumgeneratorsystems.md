---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: Funktionen SumGeneratorSystems
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: 7cb18e161dce3a52d7c9a0bf6a45d4818db2b849
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192476"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="63a96-102">Funktionen SumGeneratorSystems</span><span class="sxs-lookup"><span data-stu-id="63a96-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="63a96-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="63a96-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="63a96-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63a96-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63a96-105">Lägger till flera `GeneratorSystem` s för att skapa en ny GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="63a96-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="63a96-106">Indata</span><span class="sxs-lookup"><span data-stu-id="63a96-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="63a96-107">generatorSystems: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="63a96-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="63a96-108">En matris av typen `GeneratorSystem[]` .</span><span class="sxs-lookup"><span data-stu-id="63a96-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="63a96-109">Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="63a96-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="63a96-110">Ett `GeneratorSystem` som representerar ett system som är summan av data Generator systemen.</span><span class="sxs-lookup"><span data-stu-id="63a96-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="63a96-111">Se även</span><span class="sxs-lookup"><span data-stu-id="63a96-111">See Also</span></span>

- [<span data-ttu-id="63a96-112">Microsoft. Quantum. simulering. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="63a96-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)