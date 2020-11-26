---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: Funktionen SizeAdjustedTruthTable
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202931"
---
# <a name="sizeadjustedtruthtable-function"></a>Funktionen SizeAdjustedTruthTable

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Justerar sanningen-tabellen från matrisen med booleska värden enligt antalet variabler

En ny matris returneras som längd `2^numVars` , vilket kan kräva att storleken på utökningen är att utökas `table` med `false` poster eller trunkeras till `2^numVars` element.

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a>Indata

### <a name="table--bool"></a>Tabell: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Sanningen-tabell som en matris med sanningen-värden


### <a name="numvars--int"></a>numVars: [int](xref:microsoft.quantum.lang-ref.int)

Antal variabler



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Storlek justerad sanningen-tabell