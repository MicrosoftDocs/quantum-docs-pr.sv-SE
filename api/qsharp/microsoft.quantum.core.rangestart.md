---
uid: Microsoft.Quantum.Core.RangeStart
title: Rang funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831118"
---
# <a name="rangestart-function"></a><span data-ttu-id="5acfb-102">Rang funktion</span><span class="sxs-lookup"><span data-stu-id="5acfb-102">RangeStart function</span></span>

<span data-ttu-id="5acfb-103">Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="5acfb-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="5acfb-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5acfb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5acfb-105">Returnerar det definierade startvärdet för det angivna intervallet.</span><span class="sxs-lookup"><span data-stu-id="5acfb-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="5acfb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5acfb-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="5acfb-107">intervall: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="5acfb-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="5acfb-108">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5acfb-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5acfb-109">Det definierade startvärdet för det angivna intervallet.</span><span class="sxs-lookup"><span data-stu-id="5acfb-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="5acfb-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5acfb-110">Remarks</span></span>

<span data-ttu-id="5acfb-111">Det första elementet i ett intervall uttryck är `start` , dess andra element, det `start+step` tredje elementet är, `start+step+step` osv., tills `end` det skickas.</span><span class="sxs-lookup"><span data-stu-id="5acfb-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="5acfb-112">Observera att det definierade startvärdet för ett intervall är detsamma som det första elementet i sekvensen, om inte intervallet anger en tom sekvens (till exempel 2..</span><span class="sxs-lookup"><span data-stu-id="5acfb-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="5acfb-113">1).</span><span class="sxs-lookup"><span data-stu-id="5acfb-113">1).</span></span>