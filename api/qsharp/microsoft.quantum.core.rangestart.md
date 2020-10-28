---
uid: Microsoft.Quantum.Core.RangeStart
title: Rang funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727414"
---
# <a name="rangestart-function"></a><span data-ttu-id="c5244-102">Rang funktion</span><span class="sxs-lookup"><span data-stu-id="c5244-102">RangeStart function</span></span>

<span data-ttu-id="c5244-103">Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="c5244-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="c5244-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5244-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5244-105">Returnerar det definierade startvärdet för det angivna intervallet.</span><span class="sxs-lookup"><span data-stu-id="c5244-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="c5244-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c5244-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="c5244-107">intervall: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="c5244-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="c5244-108">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5244-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5244-109">Det definierade startvärdet för det angivna intervallet.</span><span class="sxs-lookup"><span data-stu-id="c5244-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5244-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c5244-110">Remarks</span></span>

<span data-ttu-id="c5244-111">Det första elementet i ett intervall uttryck är `start` , dess andra element, det `start+step` tredje elementet är, `start+step+step` osv., tills `end` det skickas.</span><span class="sxs-lookup"><span data-stu-id="c5244-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="c5244-112">Observera att det definierade startvärdet för ett intervall är detsamma som det första elementet i sekvensen, om inte intervallet anger en tom sekvens (till exempel 2..</span><span class="sxs-lookup"><span data-stu-id="c5244-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="c5244-113">1).</span><span class="sxs-lookup"><span data-stu-id="c5244-113">1).</span></span>