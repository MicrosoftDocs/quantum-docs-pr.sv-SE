---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196335"
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