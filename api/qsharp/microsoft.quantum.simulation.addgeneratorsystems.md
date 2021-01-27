---
uid: Microsoft.Quantum.Simulation.AddGeneratorSystems
title: Funktionen AddGeneratorSystems
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: b23fc89b941a7cdd93ee7938dda50eb14e3ed528
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857946"
---
# <a name="addgeneratorsystems-function"></a>Funktionen AddGeneratorSystems

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Lägger till två `GeneratorSystem` s för att skapa en ny `GeneratorSystem` .

```qsharp
function AddGeneratorSystems (generatorSystemA : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemB : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Indata

### <a name="generatorsystema--generatorsystem"></a>generatorSystemA: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Den första `GeneratorSystem` .


### <a name="generatorsystemb--generatorsystem"></a>generatorSystemB: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Den andra `GeneratorSystem` .



## <a name="output--generatorsystem"></a>Utdata: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Ett `GeneratorSystem` som representerar ett system som är summan av data Generator systemen.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. simulering. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)