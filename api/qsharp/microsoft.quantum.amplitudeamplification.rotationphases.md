---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731942"
---
# <a name="rotationphases-user-defined-type"></a>RotationPhases-användardefinierad typ

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paketfilerna [](https://nuget.org/packages/)


Faser för en sekvens med en qubit rotation i amplitud förstärkning.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Kommentarer

Den första parametern är en matris med faser för reflektioner, uttryckt som en produkt av en qubit rotation.
[ G.H. Låg, I. L. Chuang, https://arxiv.org/abs/1707.05391 ].