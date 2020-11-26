---
uid: Microsoft.Quantum.Core.RangeStep
title: Funktionen RangeStep
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 39c8581fe795a1b76d2a6e81c238a271287c2c38
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213811"
---
# <a name="rangestep-function"></a><span data-ttu-id="3ed11-102">Funktionen RangeStep</span><span class="sxs-lookup"><span data-stu-id="3ed11-102">RangeStep function</span></span>

<span data-ttu-id="3ed11-103">Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="3ed11-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="3ed11-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3ed11-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3ed11-105">Returnerar det heltal som anger hur nästa värde i ett intervall beräknas.</span><span class="sxs-lookup"><span data-stu-id="3ed11-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="3ed11-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3ed11-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="3ed11-107">intervall: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="3ed11-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="3ed11-108">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ed11-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ed11-109">Det definierade stegvärdet för det angivna intervallet.</span><span class="sxs-lookup"><span data-stu-id="3ed11-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="3ed11-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3ed11-110">Remarks</span></span>

<span data-ttu-id="3ed11-111">Det första elementet i ett intervall uttryck är `start` , dess andra element, det `start+step` tredje elementet är, `start+step+step` osv., tills `end` det skickas.</span><span class="sxs-lookup"><span data-stu-id="3ed11-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>