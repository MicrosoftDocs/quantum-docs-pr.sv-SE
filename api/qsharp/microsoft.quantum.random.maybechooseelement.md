---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732171"
---
# <a name="maybechooseelement-operation"></a>MaybeChooseElement-åtgärd

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paketfilerna [](https://nuget.org/packages/)


Om du har fått en data mat ris och en distribution över sina index, försöker att välja ett element slumpmässigt.

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a>Indata

### <a name="data--t"></a>data: ' t []

Matrisen som ett element ska väljas från.


### <a name="indexdistribution--discretedistribution"></a>indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

En distribution över indexen hos `data` .



## <a name="output--boolt"></a>Utdata: ([bool](xref:microsoft.quantum.lang-ref.bool), t)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

