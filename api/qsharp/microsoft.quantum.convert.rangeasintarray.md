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
# <a name="rangeasintarray-function"></a><span data-ttu-id="90e07-102">Funktionen RangeAsIntArray</span><span class="sxs-lookup"><span data-stu-id="90e07-102">RangeAsIntArray function</span></span>

<span data-ttu-id="90e07-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="90e07-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="90e07-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="90e07-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="90e07-105">Skapar en matris `arr` med heltal som räknas upp av start.. steg... ändamål.</span><span class="sxs-lookup"><span data-stu-id="90e07-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="90e07-106">Indata</span><span class="sxs-lookup"><span data-stu-id="90e07-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="90e07-107">intervall: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="90e07-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="90e07-108">En `Range` av värdena `start..step..end` som ska konverteras till en matris.</span><span class="sxs-lookup"><span data-stu-id="90e07-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="90e07-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="90e07-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="90e07-110">En ny matris med heltal som motsvarar värden som upprepas av `range` .</span><span class="sxs-lookup"><span data-stu-id="90e07-110">A new array of integers corresponding to values iterated over by `range`.</span></span>