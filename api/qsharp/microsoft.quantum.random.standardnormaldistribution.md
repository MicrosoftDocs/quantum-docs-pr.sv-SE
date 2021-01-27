---
uid: Microsoft.Quantum.Random.StandardNormalDistribution
title: Funktionen StandardNormalDistribution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: StandardNormalDistribution
qsharp.summary: Returns a normal distribution with mean 0 and variance 1.
ms.openlocfilehash: e1776339655c33516f7b3d156f1b377a0c74d250
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857801"
---
# <a name="standardnormaldistribution-function"></a>Funktionen StandardNormalDistribution

Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Returnerar en normal distribution med medelvärden 0 och varians 1.

```qsharp
function StandardNormalDistribution () : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="output--continuousdistribution"></a>Utdata: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>Exempel

Följande ritar 10 exempel från standard normal fördelningen:

```qsharp
let samples = DrawMany((StandardNormalDistribution())::Sample, 10, ());
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Random. NormalDistribution](xref:Microsoft.Quantum.Random.NormalDistribution)