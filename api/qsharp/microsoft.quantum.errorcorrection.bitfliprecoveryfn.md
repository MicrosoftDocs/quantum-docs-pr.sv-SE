---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: Funktionen BitFlipRecoveryFn
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: f8d102cd54222f61058c655e72c63e86d2f5af03
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201214"
---
# <a name="bitfliprecoveryfn-function"></a><span data-ttu-id="8d7f6-102">Funktionen BitFlipRecoveryFn</span><span class="sxs-lookup"><span data-stu-id="8d7f6-102">BitFlipRecoveryFn function</span></span>

<span data-ttu-id="8d7f6-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="8d7f6-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="8d7f6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d7f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d7f6-105">Funktion för återställnings Pauli åtgärder för angivet Syndrome mått efter tabells ökning för ⟦ 3, 1, 1 ⟧ bit flip-kod.</span><span class="sxs-lookup"><span data-stu-id="8d7f6-105">Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.</span></span>

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="8d7f6-106">Utdata: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="8d7f6-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="8d7f6-107">Funktion av typ `RecoveryFn` som tar en Syndrome-mätning `Result[]` och returnerar de `Pauli[]` åtgärder som åtgärdar det identifierade felet.</span><span class="sxs-lookup"><span data-stu-id="8d7f6-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d7f6-108">Se även</span><span class="sxs-lookup"><span data-stu-id="8d7f6-108">See Also</span></span>

- [<span data-ttu-id="8d7f6-109">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="8d7f6-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)