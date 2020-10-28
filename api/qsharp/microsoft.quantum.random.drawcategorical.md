---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730958"
---
# <a name="drawcategorical-operation"></a>DrawCategorical-åtgärd

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paketfilerna [](https://nuget.org/packages/)


Ritar ett slumpmässigt exempel från en kategoriska-distribution som anges av en lista över sannolika.

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>Beskrivning

Sannolikheten för att välja ett speciellt index är proportionerlig till värdet för mat ris elementet i det indexet.
Mat ris element som är lika med noll ignoreras och deras index returneras aldrig. Om något mat ris element är mindre än noll, eller om inget mat ris element är större än noll, så Miss lyckas åtgärden.

## <a name="input"></a>Indata

### <a name="probs--double"></a>sannolikheter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]

En matris med flytt ALS siffror som är proportionella mot sannolikheten för att välja varje index.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Ett heltal $i $ med sannolikhet $ \Pr (i) = p_i/\ sum_i p_i $, där $p _i $ är $i $ th-elementet i `probs` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Random. CategoricalDistribution](xref:Microsoft.Quantum.Random.CategoricalDistribution)