---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858413"
---
# <a name="generatorsystem-user-defined-type"></a>GeneratorSystem-användardefinierad typ

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representerar en samling `GeneratorIndex` es.

Vi itererar över den här samlingen med ett heltal för ett enda index och storleken på samlingen antas vara känd.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Kommentarer

Instanser av `GeneratorSystem` kan definieras enkelt med hjälp av <xref:microsoft.quantum.arrays.lookupfunction> funktionen.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)