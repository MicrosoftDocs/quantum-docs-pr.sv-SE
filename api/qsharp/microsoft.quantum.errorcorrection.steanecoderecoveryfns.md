---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: Funktionen SteaneCodeRecoveryFns
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 8dc715042f98b90b8cea7e2d6ecb5d02a78d297f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853031"
---
# <a name="steanecoderecoveryfns-function"></a>Funktionen SteaneCodeRecoveryFns

Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Avkodare för kombinerade X-och Z-delar av stabiliserings gruppen i ⟦ 7, 1, 3 ⟧ Steane Quantum Code.

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a>Utdata: ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))

Tupel av funktioner av typen `RecoveryFn` som tar en Syndrome-mätning `Result[]` och returnerar de `Pauli[]` åtgärder som åtgärdar det identifierade felet.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryZ](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)