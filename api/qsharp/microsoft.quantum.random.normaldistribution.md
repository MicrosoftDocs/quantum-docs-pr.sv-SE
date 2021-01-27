---
uid: Microsoft.Quantum.Random.NormalDistribution
title: Funktionen NormalDistribution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814185"
---
# <a name="normaldistribution-function"></a>Funktionen NormalDistribution

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Returnerar en normal distribution med ett angivet medelvärde och varians.

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Indata

### <a name="mean--double"></a>medelvärde: [dubbel](xref:microsoft.quantum.lang-ref.double)




### <a name="variance--double"></a>varians: [dubbel](xref:microsoft.quantum.lang-ref.double)





## <a name="output--continuousdistribution"></a>Utdata: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>Exempel

Följande ritar 10 exempel från normal distribution med medel 2 och standard avvikelse 0,1:

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Random. StandardNormalDistribution](xref:Microsoft.Quantum.Random.StandardNormalDistribution)