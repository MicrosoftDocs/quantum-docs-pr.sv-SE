---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858413"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="30a3e-102">GeneratorSystem-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="30a3e-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="30a3e-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="30a3e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="30a3e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="30a3e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="30a3e-105">Representerar en samling `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="30a3e-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="30a3e-106">Vi itererar över den här samlingen med ett heltal för ett enda index och storleken på samlingen antas vara känd.</span><span class="sxs-lookup"><span data-stu-id="30a3e-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="30a3e-107">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="30a3e-107">Remarks</span></span>

<span data-ttu-id="30a3e-108">Instanser av `GeneratorSystem` kan definieras enkelt med hjälp av <xref:microsoft.quantum.arrays.lookupfunction> funktionen.</span><span class="sxs-lookup"><span data-stu-id="30a3e-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="30a3e-109">Se även</span><span class="sxs-lookup"><span data-stu-id="30a3e-109">See Also</span></span>

- [<span data-ttu-id="30a3e-110">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="30a3e-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)