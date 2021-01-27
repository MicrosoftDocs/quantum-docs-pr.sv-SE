---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: RecoverCSS-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: c192abbdfd02b26fbdba7b11f51ed08bb1a2030f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853041"
---
# <a name="recovercss-operation"></a>RecoverCSS-åtgärd

Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utför en enskild avrundning av fel korrigering med en Quantum-kod som beskrivs av en `CSS` typ.

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>Indata

### <a name="code--css"></a>kod: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

En Quantum CSS-felkorrigering kod paketerad som en `CSS` typ beskriver kodning och avkodning av Quantum-data och hur fel syndromes ska mätas.


### <a name="fnx--recoveryfn"></a>fnX: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

En `RecoveryFn` som mappar varje $X $-fel Syndrome till de `Pauli[]` åtgärder som korrigerar det identifierade felet.


### <a name="fnz--recoveryfn"></a>fnZ: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

En `RecoveryFn` som mappar varje $Z $-fel Syndrome till de `Pauli[]` åtgärder som korrigerar det identifierade felet.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

En matris med qubits där stabiliserings koden definieras.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. ErrorCorrection. CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)