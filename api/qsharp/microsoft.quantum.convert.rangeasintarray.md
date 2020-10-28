---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: Funktionen RangeAsIntArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727498"
---
# <a name="rangeasintarray-function"></a>Funktionen RangeAsIntArray

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paketfilerna [](https://nuget.org/packages/)


Skapar en matris `arr` med heltal som räknas upp av start.. steg... ändamål.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Indata

### <a name="range--range"></a>intervall: [intervall](xref:microsoft.quantum.lang-ref.range)

En `Range` av värdena `start..step..end` som ska konverteras till en matris.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]

En ny matris med heltal som motsvarar värden som upprepas av `range` .