---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: Funktionen FiveQubitCodeRecoveryFn
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 5b8afe222d197eb7d342ac45f027f2de9130b61a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727054"
---
# <a name="fivequbitcoderecoveryfn-function"></a>Funktionen FiveQubitCodeRecoveryFn

Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paketfilerna [](https://nuget.org/packages/)


Returnerar funktion som mappar fel Syndrome mätningar till rätt fel – korrigera Pauli-operatorer efter tabells ökning för ⟦ 5, 1, 3 ⟧ Quantum Code.

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Utdata: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Funktion av typ `RecoveryFn` som tar en Syndrome-mätning `Result[]` och returnerar de `Pauli[]` operatorer som korrigerar det identifierade felet.

## <a name="remarks"></a>Kommentarer

Genom att iterera över alla fel i vikt $1 $ får vi totalt $3 \ gånger 5 = 15 $ möjligt icke-trivial syndromes.
Tillsammans med identiteten har en tabell med fel och motsvarande Syndrome skapats. För den 5 qubit koden anges följande tabell: $X \_ 1: (0, 0, 1); X \_ 2: (1,0, 0, 0); X \_ 3: (1, 1,0); X \_ 4: (0, 1, 1, 0); X \_ 5: (0,0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1,0, 0, 1); Z \_ 5: (0, 1,0) $ med $Y _i $ erhålls genom att lägga till $X _i $ och $Z _i $ syndromes. Observera att ordningen i tabell söknings återställningen anges genom att konvertera bitvectors till heltal (med little endian).

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)