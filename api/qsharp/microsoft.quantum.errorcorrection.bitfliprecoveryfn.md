---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: Funktionen BitFlipRecoveryFn
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727126"
---
# <a name="bitfliprecoveryfn-function"></a><span data-ttu-id="0f8e0-102">Funktionen BitFlipRecoveryFn</span><span class="sxs-lookup"><span data-stu-id="0f8e0-102">BitFlipRecoveryFn function</span></span>

<span data-ttu-id="0f8e0-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="0f8e0-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="0f8e0-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f8e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f8e0-105">Funktion för återställnings Pauli åtgärder för angivet Syndrome mått efter tabells ökning för ⟦ 3, 1, 1 ⟧ bit flip-kod.</span><span class="sxs-lookup"><span data-stu-id="0f8e0-105">Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.</span></span>

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="0f8e0-106">Utdata: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="0f8e0-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="0f8e0-107">Funktion av typ `RecoveryFn` som tar en Syndrome-mätning `Result[]` och returnerar de `Pauli[]` åtgärder som åtgärdar det identifierade felet.</span><span class="sxs-lookup"><span data-stu-id="0f8e0-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f8e0-108">Se även</span><span class="sxs-lookup"><span data-stu-id="0f8e0-108">See Also</span></span>

- [<span data-ttu-id="0f8e0-109">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="0f8e0-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)