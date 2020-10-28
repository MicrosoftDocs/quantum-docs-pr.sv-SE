---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: Funktionen MultiplyGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 1d28de99dab3f7aca4bf3706fe98f5ef7c5286a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730926"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="598ed-102">Funktionen MultiplyGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="598ed-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="598ed-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="598ed-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="598ed-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="598ed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="598ed-105">Multiplicerar koefficienten för alla villkor i en `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="598ed-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="598ed-106">Indata</span><span class="sxs-lookup"><span data-stu-id="598ed-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="598ed-107">multiplikator: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="598ed-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="598ed-108">Multiplikatorn för koefficienten.</span><span class="sxs-lookup"><span data-stu-id="598ed-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="598ed-109">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="598ed-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="598ed-110">`GeneratorSystem`För att multipliceras.</span><span class="sxs-lookup"><span data-stu-id="598ed-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="598ed-111">Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="598ed-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="598ed-112">En `GeneratorSystem` som representerar ett system med koefficienter som är `multiplier` större.</span><span class="sxs-lookup"><span data-stu-id="598ed-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="598ed-113">Se även</span><span class="sxs-lookup"><span data-stu-id="598ed-113">See Also</span></span>

- [<span data-ttu-id="598ed-114">Microsoft. Quantum. simulering. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="598ed-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)