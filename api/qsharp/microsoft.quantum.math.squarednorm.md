---
uid: Microsoft.Quantum.Math.SquaredNorm
title: Funktionen SquaredNorm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227309"
---
# <a name="squarednorm-function"></a>Funktionen SquaredNorm

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar kvadraten 2 – normal för en Vector.

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>Beskrivning

Returnerar kvadraten 2 – normal för en Vector; Det innebär att med en inmatad $ \vec{x} $ returneras $ \ sum_i x_i ^ 2 $.

## <a name="input"></a>Indata

### <a name="array--double"></a>matris: [dubbel](xref:microsoft.quantum.lang-ref.double)[]

Den vektor vars kvadrat 2-norm ska returneras.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)

Kvadrat 2 – normal för `array` .