---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: Funktionen MultiplyGeneratorIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: 9ee0568073b65b027cc98eb56934e9286b59c27f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733499"
---
# <a name="multiplygeneratorindex-function"></a>Funktionen MultiplyGeneratorIndex

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paketfilerna [](https://nuget.org/packages/)


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