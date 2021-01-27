---
uid: Microsoft.Quantum.Core.RangeReverse
title: Funktionen RangeReverse
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853648"
---
# <a name="rangereverse-function"></a><span data-ttu-id="17f2c-102">Funktionen RangeReverse</span><span class="sxs-lookup"><span data-stu-id="17f2c-102">RangeReverse function</span></span>

<span data-ttu-id="17f2c-103">Namnrymd: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="17f2c-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="17f2c-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="17f2c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="17f2c-105">Returnerar ett nytt intervall som är omvänt från det angivna intervallet.</span><span class="sxs-lookup"><span data-stu-id="17f2c-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="17f2c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="17f2c-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="17f2c-107">r: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="17f2c-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="17f2c-108">Indataområde.</span><span class="sxs-lookup"><span data-stu-id="17f2c-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="17f2c-109">Utdata: [intervall](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="17f2c-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="17f2c-110">Ett nytt intervall som är omvänt i det aktuella intervallet.</span><span class="sxs-lookup"><span data-stu-id="17f2c-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="17f2c-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="17f2c-111">Remarks</span></span>

<span data-ttu-id="17f2c-112">Observera att omvänt i ett intervall inte bara är `end` det enda... `-step` `start` , eftersom det sista elementet i ett intervall inte kan vara detsamma som `end` .</span><span class="sxs-lookup"><span data-stu-id="17f2c-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>