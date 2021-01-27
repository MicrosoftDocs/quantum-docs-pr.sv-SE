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
# <a name="rangeasintarray-function"></a><span data-ttu-id="e7170-102">Funktionen RangeAsIntArray</span><span class="sxs-lookup"><span data-stu-id="e7170-102">RangeAsIntArray function</span></span>

<span data-ttu-id="e7170-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="e7170-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="e7170-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7170-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7170-105">Skapar en matris `arr` med heltal som räknas upp av start.. steg... ändamål.</span><span class="sxs-lookup"><span data-stu-id="e7170-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="e7170-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e7170-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="e7170-107">intervall: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="e7170-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="e7170-108">En `Range` av värdena `start..step..end` som ska konverteras till en matris.</span><span class="sxs-lookup"><span data-stu-id="e7170-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="e7170-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e7170-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e7170-110">En ny matris med heltal som motsvarar värden som upprepas av `range` .</span><span class="sxs-lookup"><span data-stu-id="e7170-110">A new array of integers corresponding to values iterated over by `range`.</span></span>

## <a name="example"></a><span data-ttu-id="e7170-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="e7170-111">Example</span></span>

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```