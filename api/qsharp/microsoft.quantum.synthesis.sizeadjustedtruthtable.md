---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: Funktionen SizeAdjustedTruthTable
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855324"
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