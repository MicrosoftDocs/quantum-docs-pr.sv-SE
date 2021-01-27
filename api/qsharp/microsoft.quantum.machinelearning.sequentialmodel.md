---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854899"
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