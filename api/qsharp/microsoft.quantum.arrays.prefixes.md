---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefix funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220404"
---
# <a name="prefixes-function"></a>Prefix funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en matris returneras alla prefix.

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a>Beskrivning

Returnerar en matris med alla prefix, som börjar med en matris som bara har det första elementet fram till hela matrisen.

## <a name="input"></a>Indata

### <a name="array--t"></a>matris: ' ' []

En matris med element.



## <a name="output--t"></a>Utdata: ' t [] []



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av `array` element.