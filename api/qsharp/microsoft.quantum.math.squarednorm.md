---
uid: Microsoft.Quantum.Math.SquaredNorm
title: Funktionen SquaredNorm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733803"
---
# <a name="squarednorm-function"></a>Funktionen SquaredNorm

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paketfilerna [](https://nuget.org/packages/)


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