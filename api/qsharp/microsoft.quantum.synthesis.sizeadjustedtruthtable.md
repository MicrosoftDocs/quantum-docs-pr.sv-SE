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
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="99d6a-102">Funktionen SizeAdjustedTruthTable</span><span class="sxs-lookup"><span data-stu-id="99d6a-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="99d6a-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="99d6a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="99d6a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99d6a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99d6a-105">Justerar sanningen-tabellen från matrisen med booleska värden enligt antalet variabler</span><span class="sxs-lookup"><span data-stu-id="99d6a-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="99d6a-106">En ny matris returneras som längd `2^numVars` , vilket kan kräva att storleken på utökningen är att utökas `table` med `false` poster eller trunkeras till `2^numVars` element.</span><span class="sxs-lookup"><span data-stu-id="99d6a-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="99d6a-107">Indata</span><span class="sxs-lookup"><span data-stu-id="99d6a-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="99d6a-108">Tabell: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="99d6a-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="99d6a-109">Sanningen-tabell som en matris med sanningen-värden</span><span class="sxs-lookup"><span data-stu-id="99d6a-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="99d6a-110">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99d6a-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="99d6a-111">Antal variabler</span><span class="sxs-lookup"><span data-stu-id="99d6a-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="99d6a-112">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="99d6a-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="99d6a-113">Storlek justerad sanningen-tabell</span><span class="sxs-lookup"><span data-stu-id="99d6a-113">Size adjusted truth table</span></span>