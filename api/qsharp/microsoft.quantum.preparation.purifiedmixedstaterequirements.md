---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: Funktionen PurifiedMixedStateRequirements
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 6ddb48ba66eea87a07d515ff791bfb34f2d98b76
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856839"
---
# <a name="purifiedmixedstaterequirements-function"></a><span data-ttu-id="e29b4-102">Funktionen PurifiedMixedStateRequirements</span><span class="sxs-lookup"><span data-stu-id="e29b4-102">PurifiedMixedStateRequirements function</span></span>

<span data-ttu-id="e29b4-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e29b4-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e29b4-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e29b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e29b4-105">Returnerar det totala antalet qubits som måste allokeras för att åtgärden som returneras av ska kunna användas @"microsoft.quantum.preparation.purifiedmixedstate" .</span><span class="sxs-lookup"><span data-stu-id="e29b4-105">Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".</span></span>

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a><span data-ttu-id="e29b4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e29b4-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="e29b4-107">targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e29b4-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e29b4-108">Mål felet $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="e29b4-108">The target error $\epsilon$.</span></span>


### <a name="ncoefficients--int"></a><span data-ttu-id="e29b4-109">nCoefficients: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e29b4-109">nCoefficients : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e29b4-110">Antalet koefficienter som ska anges när ett blandat tillstånd förbereds.</span><span class="sxs-lookup"><span data-stu-id="e29b4-110">The number of coefficients to be specified in preparing a mixed state.</span></span>



## <a name="output--mixedstatepreparationrequirements"></a><span data-ttu-id="e29b4-111">Utdata: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="e29b4-111">Output : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>

<span data-ttu-id="e29b4-112">En beskrivning av hur många qubits som krävs totalt och för varje index och skräp register som används av @"microsoft.quantum.preparation.purifiedmixedstate" funktionen.</span><span class="sxs-lookup"><span data-stu-id="e29b4-112">A description of how many qubits are required in total, and for each of the index and garbage registers used by the @"microsoft.quantum.preparation.purifiedmixedstate" function.</span></span>

## <a name="see-also"></a><span data-ttu-id="e29b4-113">Se även</span><span class="sxs-lookup"><span data-stu-id="e29b4-113">See Also</span></span>

- [<span data-ttu-id="e29b4-114">Microsoft. Quantum. preparation. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="e29b4-114">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)