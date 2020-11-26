---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: Funktionen PurifiedMixedStateRequirements
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 9b8861a4112c4e6c9db994339353c771a3de81a6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229995"
---
# <a name="purifiedmixedstaterequirements-function"></a><span data-ttu-id="ede5a-102">Funktionen PurifiedMixedStateRequirements</span><span class="sxs-lookup"><span data-stu-id="ede5a-102">PurifiedMixedStateRequirements function</span></span>

<span data-ttu-id="ede5a-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="ede5a-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="ede5a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ede5a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ede5a-105">Returnerar det totala antalet qubits som måste allokeras för att åtgärden som returneras av ska kunna användas @"microsoft.quantum.preparation.purifiedmixedstate" .</span><span class="sxs-lookup"><span data-stu-id="ede5a-105">Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".</span></span>

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a><span data-ttu-id="ede5a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ede5a-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="ede5a-107">targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ede5a-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ede5a-108">Mål felet $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="ede5a-108">The target error $\epsilon$.</span></span>


### <a name="ncoefficients--int"></a><span data-ttu-id="ede5a-109">nCoefficients: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ede5a-109">nCoefficients : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ede5a-110">Antalet koefficienter som ska anges när ett blandat tillstånd förbereds.</span><span class="sxs-lookup"><span data-stu-id="ede5a-110">The number of coefficients to be specified in preparing a mixed state.</span></span>



## <a name="output--mixedstatepreparationrequirements"></a><span data-ttu-id="ede5a-111">Utdata: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="ede5a-111">Output : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>

<span data-ttu-id="ede5a-112">En beskrivning av hur många qubits som krävs totalt och för varje index och skräp register som används av @"microsoft.quantum.preparation.purifiedmixedstate" funktionen.</span><span class="sxs-lookup"><span data-stu-id="ede5a-112">A description of how many qubits are required in total, and for each of the index and garbage registers used by the @"microsoft.quantum.preparation.purifiedmixedstate" function.</span></span>

## <a name="see-also"></a><span data-ttu-id="ede5a-113">Se även</span><span class="sxs-lookup"><span data-stu-id="ede5a-113">See Also</span></span>

- [<span data-ttu-id="ede5a-114">Microsoft. Quantum. preparation. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="ede5a-114">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)