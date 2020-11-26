---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225235"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="ab6c3-102">GeneratorSystem-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="ab6c3-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="ab6c3-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ab6c3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ab6c3-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab6c3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab6c3-105">Representerar en samling `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="ab6c3-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="ab6c3-106">Vi itererar över den här samlingen med ett heltal för ett enda index och storleken på samlingen antas vara känd.</span><span class="sxs-lookup"><span data-stu-id="ab6c3-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="ab6c3-107">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ab6c3-107">Remarks</span></span>

<span data-ttu-id="ab6c3-108">Instanser av `GeneratorSystem` kan definieras enkelt med hjälp av <xref:microsoft.quantum.arrays.lookupfunction> funktionen.</span><span class="sxs-lookup"><span data-stu-id="ab6c3-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab6c3-109">Se även</span><span class="sxs-lookup"><span data-stu-id="ab6c3-109">See Also</span></span>

- [<span data-ttu-id="ab6c3-110">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="ab6c3-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)