---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: Funktionen SteaneCodeRecoveryFns
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: b1dd1c2e9a71e58bd8a86d1759a8b6af13a49614
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726973"
---
# <a name="steanecoderecoveryfns-function"></a><span data-ttu-id="e2065-102">Funktionen SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="e2065-102">SteaneCodeRecoveryFns function</span></span>

<span data-ttu-id="e2065-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e2065-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e2065-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e2065-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e2065-105">Avkodare för kombinerade X-och Z-delar av stabiliserings gruppen i ⟦ 7, 1, 3 ⟧ Steane Quantum Code.</span><span class="sxs-lookup"><span data-stu-id="e2065-105">Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a><span data-ttu-id="e2065-106">Utdata: ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))</span><span class="sxs-lookup"><span data-stu-id="e2065-106">Output : ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))</span></span>

<span data-ttu-id="e2065-107">Tupel av funktioner av typen `RecoveryFn` som tar en Syndrome-mätning `Result[]` och returnerar de `Pauli[]` åtgärder som åtgärdar det identifierade felet.</span><span class="sxs-lookup"><span data-stu-id="e2065-107">Tuple of functions of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2065-108">Se även</span><span class="sxs-lookup"><span data-stu-id="e2065-108">See Also</span></span>

- [<span data-ttu-id="e2065-109">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="e2065-109">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="e2065-110">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryZ</span><span class="sxs-lookup"><span data-stu-id="e2065-110">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)