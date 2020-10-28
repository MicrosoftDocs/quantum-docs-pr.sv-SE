---
uid: Microsoft.Quantum.Core.RangeStep
title: Funktionen RangeStep
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727411"
---
# <a name="rangestep-function"></a><span data-ttu-id="86da5-102">Funktionen RangeStep</span><span class="sxs-lookup"><span data-stu-id="86da5-102">RangeStep function</span></span>

<span data-ttu-id="86da5-103">Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="86da5-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="86da5-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="86da5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="86da5-105">Returnerar det heltal som anger hur nästa värde i ett intervall beräknas.</span><span class="sxs-lookup"><span data-stu-id="86da5-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="86da5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="86da5-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="86da5-107">intervall: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="86da5-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="86da5-108">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="86da5-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="86da5-109">Det definierade stegvärdet för det angivna intervallet.</span><span class="sxs-lookup"><span data-stu-id="86da5-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="86da5-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="86da5-110">Remarks</span></span>

<span data-ttu-id="86da5-111">Det första elementet i ett intervall uttryck är `start` , dess andra element, det `start+step` tredje elementet är, `start+step+step` osv., tills `end` det skickas.</span><span class="sxs-lookup"><span data-stu-id="86da5-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>