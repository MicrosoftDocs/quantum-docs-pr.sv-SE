---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: Funktionen BitFlipRecoveryFn
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: 1cf2bd944b4dcaadeeca96fa0f576250590962e0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827600"
---
# <a name="bitfliprecoveryfn-function"></a><span data-ttu-id="74445-102">Funktionen BitFlipRecoveryFn</span><span class="sxs-lookup"><span data-stu-id="74445-102">BitFlipRecoveryFn function</span></span>

<span data-ttu-id="74445-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="74445-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="74445-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="74445-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="74445-105">Funktion för återställnings Pauli åtgärder för angivet Syndrome mått efter tabells ökning för ⟦ 3, 1, 1 ⟧ bit flip-kod.</span><span class="sxs-lookup"><span data-stu-id="74445-105">Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.</span></span>

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="74445-106">Utdata: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="74445-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="74445-107">Funktion av typ `RecoveryFn` som tar en Syndrome-mätning `Result[]` och returnerar de `Pauli[]` åtgärder som åtgärdar det identifierade felet.</span><span class="sxs-lookup"><span data-stu-id="74445-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="74445-108">Se även</span><span class="sxs-lookup"><span data-stu-id="74445-108">See Also</span></span>

- [<span data-ttu-id="74445-109">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="74445-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)