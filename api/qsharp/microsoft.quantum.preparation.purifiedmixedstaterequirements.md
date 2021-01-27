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
# <a name="purifiedmixedstaterequirements-function"></a>Funktionen PurifiedMixedStateRequirements

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar det totala antalet qubits som måste allokeras för att åtgärden som returneras av ska kunna användas @"microsoft.quantum.preparation.purifiedmixedstate" .

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a>Indata

### <a name="targeterror--double"></a>targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)

Mål felet $ \epsilon $.


### <a name="ncoefficients--int"></a>nCoefficients: [int](xref:microsoft.quantum.lang-ref.int)

Antalet koefficienter som ska anges när ett blandat tillstånd förbereds.



## <a name="output--mixedstatepreparationrequirements"></a>Utdata: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)

En beskrivning av hur många qubits som krävs totalt och för varje index och skräp register som används av @"microsoft.quantum.preparation.purifiedmixedstate" funktionen.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. preparation. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)