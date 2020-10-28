---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefix funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730062"
---
# <a name="prefixes-function"></a>Prefix funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paketfilerna [](https://nuget.org/packages/)


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