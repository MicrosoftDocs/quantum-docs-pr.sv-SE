---
uid: Microsoft.Quantum.Math.SquaredNorm
title: Funktionen SquaredNorm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848220"
---
# <a name="squarednorm-function"></a>Funktionen SquaredNorm

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar kvadraten 2 – normal för en Vector.

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>Description

Returnerar kvadraten 2 – normal för en Vector; Det innebär att med en inmatad $ \vec{x} $ returneras $ \ sum_i x_i ^ 2 $.

## <a name="input"></a>Indata

### <a name="array--double"></a>matris: [dubbel](xref:microsoft.quantum.lang-ref.double)[]

Den vektor vars kvadrat 2-norm ska returneras.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)

Kvadrat 2 – normal för `array` .