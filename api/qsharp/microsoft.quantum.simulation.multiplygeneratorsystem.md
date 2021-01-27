---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: Funktionen MultiplyGeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: cebd08c86ad8a3793ba7d0e9ce241d7a1ef046ae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858500"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="bcb5d-102">Funktionen MultiplyGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="bcb5d-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="bcb5d-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bcb5d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bcb5d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bcb5d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bcb5d-105">Multiplicerar koefficienten för alla villkor i en `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="bcb5d-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="bcb5d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="bcb5d-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="bcb5d-107">multiplikator: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bcb5d-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bcb5d-108">Multiplikatorn för koefficienten.</span><span class="sxs-lookup"><span data-stu-id="bcb5d-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="bcb5d-109">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="bcb5d-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="bcb5d-110">`GeneratorSystem`För att multipliceras.</span><span class="sxs-lookup"><span data-stu-id="bcb5d-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="bcb5d-111">Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="bcb5d-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="bcb5d-112">En `GeneratorSystem` som representerar ett system med koefficienter som är `multiplier` större.</span><span class="sxs-lookup"><span data-stu-id="bcb5d-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="bcb5d-113">Se även</span><span class="sxs-lookup"><span data-stu-id="bcb5d-113">See Also</span></span>

- [<span data-ttu-id="bcb5d-114">Microsoft. Quantum. simulering. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="bcb5d-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)