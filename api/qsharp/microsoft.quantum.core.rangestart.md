---
uid: Microsoft.Quantum.Core.RangeStart
title: Rang funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 44683b204ecd469f5f5412a7ec06e98ec8a4f37e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224011"
---
# <a name="rangestart-function"></a><span data-ttu-id="58844-102">Rang funktion</span><span class="sxs-lookup"><span data-stu-id="58844-102">RangeStart function</span></span>

<span data-ttu-id="58844-103">Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="58844-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="58844-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="58844-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="58844-105">Returnerar det definierade startvärdet för det angivna intervallet.</span><span class="sxs-lookup"><span data-stu-id="58844-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="58844-106">Indata</span><span class="sxs-lookup"><span data-stu-id="58844-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="58844-107">intervall: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="58844-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="58844-108">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="58844-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="58844-109">Det definierade startvärdet för det angivna intervallet.</span><span class="sxs-lookup"><span data-stu-id="58844-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="58844-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="58844-110">Remarks</span></span>

<span data-ttu-id="58844-111">Det första elementet i ett intervall uttryck är `start` , dess andra element, det `start+step` tredje elementet är, `start+step+step` osv., tills `end` det skickas.</span><span class="sxs-lookup"><span data-stu-id="58844-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="58844-112">Observera att det definierade startvärdet för ett intervall är detsamma som det första elementet i sekvensen, om inte intervallet anger en tom sekvens (till exempel 2..</span><span class="sxs-lookup"><span data-stu-id="58844-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="58844-113">1).</span><span class="sxs-lookup"><span data-stu-id="58844-113">1).</span></span>