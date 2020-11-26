---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: Funktionen MultiplyGeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: effb9e3ca754f77bbe1ea0fb6ca30ae49e92d531
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229162"
---
# <a name="multiplygeneratorsystem-function"></a>Funktionen MultiplyGeneratorSystem

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Multiplicerar koefficienten för alla villkor i en `GeneratorSystem` .

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Indata

### <a name="multiplier--double"></a>multiplikator: [dubbel](xref:microsoft.quantum.lang-ref.double)

Multiplikatorn för koefficienten.


### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`För att multipliceras.



## <a name="output--generatorsystem"></a>Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

En `GeneratorSystem` som representerar ett system med koefficienter som är `multiplier` större.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. simulering. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)