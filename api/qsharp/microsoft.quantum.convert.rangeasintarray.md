---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: Funktionen RangeAsIntArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214015"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="fb57e-102">Funktionen RangeAsIntArray</span><span class="sxs-lookup"><span data-stu-id="fb57e-102">RangeAsIntArray function</span></span>

<span data-ttu-id="fb57e-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="fb57e-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="fb57e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb57e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb57e-105">Skapar en matris `arr` med heltal som räknas upp av start.. steg... ändamål.</span><span class="sxs-lookup"><span data-stu-id="fb57e-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="fb57e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="fb57e-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="fb57e-107">intervall: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="fb57e-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="fb57e-108">En `Range` av värdena `start..step..end` som ska konverteras till en matris.</span><span class="sxs-lookup"><span data-stu-id="fb57e-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="fb57e-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fb57e-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fb57e-110">En ny matris med heltal som motsvarar värden som upprepas av `range` .</span><span class="sxs-lookup"><span data-stu-id="fb57e-110">A new array of integers corresponding to values iterated over by `range`.</span></span>