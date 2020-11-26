---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: Funktionen MultiplyGeneratorIndex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: dc2bd02c40b53eca726f70578e3c5918add8f1bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230454"
---
# <a name="multiplygeneratorindex-function"></a>Funktionen MultiplyGeneratorIndex

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Multiplicerar koefficienten i a `GeneratorIndex` .

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Indata

### <a name="multiplier--double"></a>multiplikator: [dubbel](xref:microsoft.quantum.lang-ref.double)

Multiplikatorn för koefficienten.


### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex`För att multipliceras.



## <a name="output--generatorindex"></a>Utdata: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

En `GeneratorIndex` som representerar en period med koefficienten faktor `multiplier` större.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. simulering. GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)