---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: Funktionen RangeAsIntArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850105"
---
# <a name="rangeasintarray-function"></a>Funktionen RangeAsIntArray

Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Skapar en matris `arr` med heltal som räknas upp av start.. steg... ändamål.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Indata

### <a name="range--range"></a>intervall: [intervall](xref:microsoft.quantum.lang-ref.range)

En `Range` av värdena `start..step..end` som ska konverteras till en matris.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]

En ny matris med heltal som motsvarar värden som upprepas av `range` .

## <a name="example"></a>Exempel

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```