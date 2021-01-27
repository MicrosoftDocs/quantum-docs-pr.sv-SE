---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: Funktionen TargetStateReflectionOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 4169ccf3e210e27f779311553b845ea04f2c7dc6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843896"
---
# <a name="targetstatereflectionoracle-function"></a>Funktionen TargetStateReflectionOracle

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Skapar en `ReflectionOracle` om mål tillstånd som har marker ATS unikt av flaggan qubit.

Mål status har en enda qubit inställd på 1, och alla andra 0: $ \ket {1} _F $.

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a>Indata

### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Index för att flagga qubit $f $ för Oracle.



## <a name="output--reflectionoracle"></a>Utdata: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

En `ReflectionOracle` som visar om det tillstånd som har marker ATS med $ \ket {1} _F $.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ReflectionOracle](xref:Microsoft.Quantum.Canon.ReflectionOracle)