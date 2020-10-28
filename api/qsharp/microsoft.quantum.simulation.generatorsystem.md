---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733539"
---
# <a name="generatorsystem-user-defined-type"></a>GeneratorSystem-användardefinierad typ

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paketfilerna [](https://nuget.org/packages/)


Representerar en samling `GeneratorIndex` es.

Vi itererar över den här samlingen med ett heltal för ett enda index och storleken på samlingen antas vara känd.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Kommentarer

Instanser av `GeneratorSystem` kan definieras enkelt med hjälp av <xref:microsoft.quantum.arrays.lookupfunction> funktionen.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)