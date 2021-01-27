---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856118"
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



## <a name="example"></a>Exempel

Följande Q #-kodfragment väljer ett element slumpmässigt från en matris:

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```