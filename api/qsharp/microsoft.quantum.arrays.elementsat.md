---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: Funktionen ElementsAt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: 83b5e97085234e8249869f858400cba265d13058
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221461"
---
# <a name="elementsat-function"></a>Funktionen ElementsAt

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar matrisens element i ett angivet intervall av index.

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a>Indata

### <a name="range--range"></a>intervall: [intervall](xref:microsoft.quantum.lang-ref.range)

Intervall med mat ris index


### <a name="array--t"></a>matris: ' ' []

Matris



## <a name="output--t"></a>Utdata: ' t []



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för varje element i `array` .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Arrays. ElementAt](xref:Microsoft.Quantum.Arrays.ElementAt)
- [Microsoft. Quantum. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)