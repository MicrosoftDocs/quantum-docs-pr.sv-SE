---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: Funktionen InterpolateGeneratorSystemsImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: a902a93968d221349f9a6fa977bbc1706971fcfd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855755"
---
# <a name="interpolategeneratorsystemsimpl-function"></a>Funktionen InterpolateGeneratorSystemsImpl

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Interpolerar linjärt mellan två `GeneratorSystems` enligt en schema parameter `s` mellan 0 och 1 (inklusive).

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Indata

### <a name="schedule--double"></a>schema: [dubbel](xref:microsoft.quantum.lang-ref.double)

En schema parameter $s \in [0, 1] $.


### <a name="generatorsystemstart--generatorsystem"></a>generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Start `GeneratorSystem` .


### <a name="generatorsystemend--generatorsystem"></a>generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Slutet `GeneratorSystem` .



## <a name="output--generatorsystem"></a>Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Ett `GeneratorSystem` som representerar ett system som är summan av data Generator systemen, med en vikt på $ (1-s) $ på `generatorSystemStart` och vikt $s $ på `generatorSystemEnd` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. simulering. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)