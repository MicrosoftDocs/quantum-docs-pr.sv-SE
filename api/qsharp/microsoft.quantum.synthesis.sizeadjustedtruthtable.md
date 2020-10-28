---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: Funktionen SizeAdjustedTruthTable
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 3480f022df7a289594b003f201d16d8bf7c29d7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734059"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="deeaf-102">Funktionen SizeAdjustedTruthTable</span><span class="sxs-lookup"><span data-stu-id="deeaf-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="deeaf-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="deeaf-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="deeaf-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="deeaf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="deeaf-105">Justerar sanningen-tabellen från matrisen med booleska värden enligt antalet variabler</span><span class="sxs-lookup"><span data-stu-id="deeaf-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="deeaf-106">En ny matris returneras som längd `2^numVars` , vilket kan kräva att storleken på utökningen är att utökas `table` med `false` poster eller trunkeras till `2^numVars` element.</span><span class="sxs-lookup"><span data-stu-id="deeaf-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="deeaf-107">Indata</span><span class="sxs-lookup"><span data-stu-id="deeaf-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="deeaf-108">Tabell: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="deeaf-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="deeaf-109">Sanningen-tabell som en matris med sanningen-värden</span><span class="sxs-lookup"><span data-stu-id="deeaf-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="deeaf-110">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="deeaf-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="deeaf-111">Antal variabler</span><span class="sxs-lookup"><span data-stu-id="deeaf-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="deeaf-112">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="deeaf-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="deeaf-113">Storlek justerad sanningen-tabell</span><span class="sxs-lookup"><span data-stu-id="deeaf-113">Size adjusted truth table</span></span>