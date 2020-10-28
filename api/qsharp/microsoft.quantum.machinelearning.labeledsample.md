---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726628"
---
# <a name="labeledsample-user-defined-type"></a>LabeledSample-användardefinierad typ

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


Ett exempel som kallas för en klass som exemplet tillhör.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="features--double"></a>Funktioner: [Double](xref:microsoft.quantum.lang-ref.double)[]

En Vector med funktioner för det aktuella exemplet.
### <a name="label--int"></a>Etikett: [int](xref:microsoft.quantum.lang-ref.int)

En heltals etikett för klassen som exemplet tillhör.