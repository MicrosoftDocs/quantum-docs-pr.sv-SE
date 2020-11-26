---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196182"
---
# <a name="sequentialmodel-user-defined-type"></a>SequentialModel-användardefinierad typ

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Beskriver en Quantum klassificerare-modell som består av en sekvens av parameterstyrda och kontrollerade rotationer, en tilldelning av rotations vinklar och en förskjutning mellan de två klasserna som identifieras av modellen.

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="structure--controlledrotation"></a>Struktur: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Sekvensen med kontrollerade rotationer som används för att klassificera indata.
### <a name="parameters--double"></a>Parametrar: [Double](xref:microsoft.quantum.lang-ref.double)[]

En tilldelning av rotations vinklar till den aktuella klassificerings strukturen.
### <a name="bias--double"></a>Bias: [dubbel](xref:microsoft.quantum.lang-ref.double)

Förskjutningen mellan de två klasserna som känns igen av denna klassificerare.

## <a name="references"></a>Referenser

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)