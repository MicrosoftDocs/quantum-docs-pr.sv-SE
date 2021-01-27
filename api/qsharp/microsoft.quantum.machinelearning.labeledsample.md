---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846966"
---
# <a name="labeledsample-user-defined-type"></a>LabeledSample-användardefinierad typ

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Ett exempel som kallas för en klass som exemplet tillhör.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="features--double"></a>Funktioner: [Double](xref:microsoft.quantum.lang-ref.double)[]

En Vector med funktioner för det aktuella exemplet.
### <a name="label--int"></a>Etikett: [int](xref:microsoft.quantum.lang-ref.int)

En heltals etikett för klassen som exemplet tillhör.