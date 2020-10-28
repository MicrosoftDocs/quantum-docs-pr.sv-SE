---
uid: Microsoft.Quantum.Core.RangeEnd
title: Funktionen RangeEnd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727447"
---
# <a name="rangeend-function"></a><span data-ttu-id="4bf94-102">Funktionen RangeEnd</span><span class="sxs-lookup"><span data-stu-id="4bf94-102">RangeEnd function</span></span>

<span data-ttu-id="4bf94-103">Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="4bf94-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="4bf94-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4bf94-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4bf94-105">Returnerar det definierade slutvärdet för det angivna intervallet, som inte nödvändigt vis är det sista elementet i sekvensen.</span><span class="sxs-lookup"><span data-stu-id="4bf94-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="4bf94-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4bf94-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="4bf94-107">intervall: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="4bf94-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="4bf94-108">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4bf94-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4bf94-109">Det definierade slutvärdet för det angivna intervallet.</span><span class="sxs-lookup"><span data-stu-id="4bf94-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="4bf94-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4bf94-110">Remarks</span></span>

<span data-ttu-id="4bf94-111">Det första elementet i ett intervall uttryck är `start` , dess andra element, det `start+step` tredje elementet är, `start+step+step` osv., tills `end` det skickas.</span><span class="sxs-lookup"><span data-stu-id="4bf94-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="4bf94-112">Observera att det definierade slutvärdet för ett intervall kan skilja sig från det sista elementet i den sekvens som anges av intervallet; till exempel i intervallet 0...</span><span class="sxs-lookup"><span data-stu-id="4bf94-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="4bf94-113">2..</span><span class="sxs-lookup"><span data-stu-id="4bf94-113">2 ..</span></span> <span data-ttu-id="4bf94-114">5 det sista elementet är 4 men end-värdet är 5.</span><span class="sxs-lookup"><span data-stu-id="4bf94-114">5 the last element is 4 but the end value is 5.</span></span>