---
uid: Microsoft.Quantum.Core.RangeEnd
title: Funktionen RangeEnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 196fab0bd97a441a16976033dc0d660c54cdfd6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831372"
---
# <a name="rangeend-function"></a><span data-ttu-id="5b538-102">Funktionen RangeEnd</span><span class="sxs-lookup"><span data-stu-id="5b538-102">RangeEnd function</span></span>

<span data-ttu-id="5b538-103">Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="5b538-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="5b538-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5b538-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5b538-105">Returnerar det definierade slutvärdet för det angivna intervallet, som inte nödvändigt vis är det sista elementet i sekvensen.</span><span class="sxs-lookup"><span data-stu-id="5b538-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="5b538-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5b538-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="5b538-107">intervall: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="5b538-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="5b538-108">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5b538-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5b538-109">Det definierade slutvärdet för det angivna intervallet.</span><span class="sxs-lookup"><span data-stu-id="5b538-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="5b538-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5b538-110">Remarks</span></span>

<span data-ttu-id="5b538-111">Det första elementet i ett intervall uttryck är `start` , dess andra element, det `start+step` tredje elementet är, `start+step+step` osv., tills `end` det skickas.</span><span class="sxs-lookup"><span data-stu-id="5b538-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="5b538-112">Observera att det definierade slutvärdet för ett intervall kan skilja sig från det sista elementet i den sekvens som anges av intervallet; till exempel i intervallet 0...</span><span class="sxs-lookup"><span data-stu-id="5b538-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="5b538-113">2..</span><span class="sxs-lookup"><span data-stu-id="5b538-113">2 ..</span></span> <span data-ttu-id="5b538-114">5 det sista elementet är 4 men end-värdet är 5.</span><span class="sxs-lookup"><span data-stu-id="5b538-114">5 the last element is 4 but the end value is 5.</span></span>