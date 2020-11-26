---
uid: Microsoft.Quantum.Arrays.Any
title: Alla funktioner
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: 717ab9ebcbb864a6faf1c14cd36125e589849f2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221665"
---
# <a name="any-function"></a><span data-ttu-id="34d3b-102">Alla funktioner</span><span class="sxs-lookup"><span data-stu-id="34d3b-102">Any function</span></span>

<span data-ttu-id="34d3b-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="34d3b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="34d3b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34d3b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34d3b-105">Med en matris och ett predikat som har definierats för elementen i matrisen, kontrollerar om minst ett element i matrisen uppfyller predikatet.</span><span class="sxs-lookup"><span data-stu-id="34d3b-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="34d3b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="34d3b-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="34d3b-107">predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="34d3b-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="34d3b-108">En funktion från `'T` till `Bool` som används för att kontrol lera element.</span><span class="sxs-lookup"><span data-stu-id="34d3b-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="34d3b-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="34d3b-109">array : 'T[]</span></span>

<span data-ttu-id="34d3b-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="34d3b-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="34d3b-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="34d3b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="34d3b-112">Ett `Bool` värde på eller-funktionen för predikatet som används för alla element.</span><span class="sxs-lookup"><span data-stu-id="34d3b-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="34d3b-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="34d3b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="34d3b-114">Inte</span><span class="sxs-lookup"><span data-stu-id="34d3b-114">'T</span></span>

<span data-ttu-id="34d3b-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="34d3b-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="34d3b-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="34d3b-116">Remarks</span></span>

<span data-ttu-id="34d3b-117">Funktionen definieras för generiska typer, dvs. När vi har en matris `'T[]` och en funktion `predicate: 'T -> Bool` kan vi skapa ett `Bool` värde som anger om ett element uppfyller sig `predicate` .</span><span class="sxs-lookup"><span data-stu-id="34d3b-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>