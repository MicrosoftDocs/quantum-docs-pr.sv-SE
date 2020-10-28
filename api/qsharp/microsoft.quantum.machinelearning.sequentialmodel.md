---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: a425d2155489384ca81ef1c00a5e842bcfb40ae7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732299"
---
# <a name="sequentialmodel-user-defined-type"></a>SequentialModel-användardefinierad typ

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


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