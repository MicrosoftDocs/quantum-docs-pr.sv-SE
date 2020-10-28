---
uid: Microsoft.Quantum.Core.RangeReverse
title: Funktionen RangeReverse
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727441"
---
# <a name="rangereverse-function"></a><span data-ttu-id="a304b-102">Funktionen RangeReverse</span><span class="sxs-lookup"><span data-stu-id="a304b-102">RangeReverse function</span></span>

<span data-ttu-id="a304b-103">Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="a304b-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="a304b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a304b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a304b-105">Returnerar ett nytt intervall som är omvänt från det angivna intervallet.</span><span class="sxs-lookup"><span data-stu-id="a304b-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="a304b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a304b-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="a304b-107">r: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="a304b-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="a304b-108">Indataområde.</span><span class="sxs-lookup"><span data-stu-id="a304b-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="a304b-109">Utdata: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="a304b-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="a304b-110">Ett nytt intervall som är omvänt i det aktuella intervallet.</span><span class="sxs-lookup"><span data-stu-id="a304b-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="a304b-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a304b-111">Remarks</span></span>

<span data-ttu-id="a304b-112">Observera att omvänt i ett intervall inte bara är `end` det enda... `-step` `start` , eftersom det sista elementet i ett intervall inte kan vara detsamma som `end` .</span><span class="sxs-lookup"><span data-stu-id="a304b-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>