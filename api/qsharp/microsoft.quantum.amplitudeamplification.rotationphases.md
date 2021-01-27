---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843969"
---
# <a name="rotationphases-user-defined-type"></a>RotationPhases-användardefinierad typ

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Faser för en sekvens med en qubit rotation i amplitud förstärkning.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Kommentarer

Den första parametern är en matris med faser för reflektioner, uttryckt som en produkt av en qubit rotation.
[ G.H. Låg, I. L. Chuang, https://arxiv.org/abs/1707.05391 ].