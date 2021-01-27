---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a9fe1b08e80abc65a5c4b803f0cb8a5e7a62759c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851159"
---
# <a name="drawcategorical-operation"></a>DrawCategorical-åtgärd

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Ritar ett slumpmässigt exempel från en kategoriska-distribution som anges av en lista över sannolika.

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>Description

Sannolikheten för att välja ett speciellt index är proportionerlig till värdet för mat ris elementet i det indexet.
Mat ris element som är lika med noll ignoreras och deras index returneras aldrig. Om något mat ris element är mindre än noll, eller om inget mat ris element är större än noll, så Miss lyckas åtgärden.

## <a name="input"></a>Indata

### <a name="probs--double"></a>sannolikheter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]

En matris med flytt ALS siffror som är proportionella mot sannolikheten för att välja varje index.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Ett heltal $i $ med sannolikhet $ \Pr (i) = p_i/\ sum_i p_i $, där $p _i $ är $i $ th-elementet i `probs` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Random. CategoricalDistribution](xref:Microsoft.Quantum.Random.CategoricalDistribution)