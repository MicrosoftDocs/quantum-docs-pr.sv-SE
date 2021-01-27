---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 762dac81ea0963443f0338cea1b879856c84b0ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858388"
---
# <a name="generatorindex-user-defined-type"></a>GeneratorIndex-användardefinierad typ

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representerar en enda primitiv term i uppsättningen med alla dynamiska generatorer, t. ex. Hermitian-operatörer, för vilka det finns en karta från den generatorn till tids utveckling av generatorn `EvolutionSet` .

Det första elementet (int [], Double []) är index som en term, men Pauli-strängen XXY med koefficient 0,5 skulle indexeras av ([1, 1, 2], [0,5]). Alternativt kan Hamiltonians parameterstyrda av en kontinuerlig variabel, till exempel X cos φ + Y sin φ, representeras av ([], [φ]). Det andra elementet indexerar under systemet som generatorn agerar på.

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a>Exempel

Med hjälp av  <xref:microsoft.quantum.simulation.paulievolutionset> operatorn $ \pi X_2 X_5 Y_9 $ visas följande:

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a>Kommentarer

> [!WARNING]
> Tolkningen av en `GeneratorIndex` har inte definierats, förutom med referens till en viss uppsättning generatorer.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. simulering. EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [Microsoft. Quantum. simulering. PauliEvolutionSet](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)