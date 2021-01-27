---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: Funktionen FiveQubitCodeRecoveryFn
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 94b6c12f31b0e6367151d0ebb225cff5f82915e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853134"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="512a8-102">Funktionen FiveQubitCodeRecoveryFn</span><span class="sxs-lookup"><span data-stu-id="512a8-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="512a8-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="512a8-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="512a8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="512a8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="512a8-105">Returnerar funktion som mappar fel Syndrome mätningar till rätt fel – korrigera Pauli-operatorer efter tabells ökning för ⟦ 5, 1, 3 ⟧ Quantum Code.</span><span class="sxs-lookup"><span data-stu-id="512a8-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="512a8-106">Utdata: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="512a8-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="512a8-107">Funktion av typ `RecoveryFn` som tar en Syndrome-mätning `Result[]` och returnerar de `Pauli[]` operatorer som korrigerar det identifierade felet.</span><span class="sxs-lookup"><span data-stu-id="512a8-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="512a8-108">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="512a8-108">Remarks</span></span>

<span data-ttu-id="512a8-109">Genom att iterera över alla fel i vikt $1 $ får vi totalt $3 \ gånger 5 = 15 $ möjligt icke-trivial syndromes.</span><span class="sxs-lookup"><span data-stu-id="512a8-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="512a8-110">Tillsammans med identiteten har en tabell med fel och motsvarande Syndrome skapats.</span><span class="sxs-lookup"><span data-stu-id="512a8-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="512a8-111">För den 5 qubit koden anges följande tabell: $X \_ 1: (0, 0, 1); X \_ 2: (1,0, 0, 0); X \_ 3: (1, 1,0); X \_ 4: (0, 1, 1, 0); X \_ 5: (0,0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1,0, 0, 1); Z \_ 5: (0, 1,0) $ med $Y _i $ erhålls genom att lägga till $X _i $ och $Z _i $ syndromes.</span><span class="sxs-lookup"><span data-stu-id="512a8-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="512a8-112">Observera att ordningen i tabell söknings återställningen anges genom att konvertera bitvectors till heltal (med little endian).</span><span class="sxs-lookup"><span data-stu-id="512a8-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="512a8-113">Se även</span><span class="sxs-lookup"><span data-stu-id="512a8-113">See Also</span></span>

- [<span data-ttu-id="512a8-114">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="512a8-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)