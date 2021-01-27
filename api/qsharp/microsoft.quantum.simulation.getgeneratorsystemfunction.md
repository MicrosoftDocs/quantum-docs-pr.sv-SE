---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: Funktionen GetGeneratorSystemFunction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 7b6eabd203cecf8c64f0bff3e06f08a0bec31bf2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852778"
---
# <a name="getgeneratorsystemfunction-function"></a>Funktionen GetGeneratorSystemFunction

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Hämtar `GeneratorIndex` funktionen i en `GeneratorSystem` .

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a>Indata

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Av intresse.



## <a name="output--int---generatorindex"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

En funktion som indexerar varje `GeneratorIndex` term i en Hamiltonian.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. simulering. GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [Microsoft. Quantum. simulering. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)