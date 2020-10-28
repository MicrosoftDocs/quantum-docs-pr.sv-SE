---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733539"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="49541-102">GeneratorSystem-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="49541-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="49541-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="49541-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="49541-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="49541-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="49541-105">Representerar en samling `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="49541-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="49541-106">Vi itererar över den här samlingen med ett heltal för ett enda index och storleken på samlingen antas vara känd.</span><span class="sxs-lookup"><span data-stu-id="49541-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="49541-107">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="49541-107">Remarks</span></span>

<span data-ttu-id="49541-108">Instanser av `GeneratorSystem` kan definieras enkelt med hjälp av <xref:microsoft.quantum.arrays.lookupfunction> funktionen.</span><span class="sxs-lookup"><span data-stu-id="49541-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="49541-109">Se även</span><span class="sxs-lookup"><span data-stu-id="49541-109">See Also</span></span>

- [<span data-ttu-id="49541-110">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="49541-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)