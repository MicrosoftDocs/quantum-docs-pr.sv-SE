---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192867"
---
# <a name="maybechooseelement-operation"></a>MaybeChooseElement-åtgärd

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

