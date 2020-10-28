---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: Funktionen TargetStateReflectionOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: a6ed0397be57ef6f14a712749cc416e1fd98b71c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731918"
---
# <a name="targetstatereflectionoracle-function"></a>Funktionen TargetStateReflectionOracle

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paketfilerna [](https://nuget.org/packages/)


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