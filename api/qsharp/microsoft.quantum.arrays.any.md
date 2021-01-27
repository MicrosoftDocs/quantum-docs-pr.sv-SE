---
uid: Microsoft.Quantum.Arrays.Any
title: Alla funktioner
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: a05f9531168bf2b32977665d38cc00f3c8e64879
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846269"
---
# <a name="any-function"></a><span data-ttu-id="ec46f-102">Alla funktioner</span><span class="sxs-lookup"><span data-stu-id="ec46f-102">Any function</span></span>

<span data-ttu-id="ec46f-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ec46f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ec46f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec46f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec46f-105">Med en matris och ett predikat som har definierats för elementen i matrisen, kontrollerar om minst ett element i matrisen uppfyller predikatet.</span><span class="sxs-lookup"><span data-stu-id="ec46f-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="ec46f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ec46f-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="ec46f-107">predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ec46f-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ec46f-108">En funktion från `'T` till `Bool` som används för att kontrol lera element.</span><span class="sxs-lookup"><span data-stu-id="ec46f-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="ec46f-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="ec46f-109">array : 'T[]</span></span>

<span data-ttu-id="ec46f-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="ec46f-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ec46f-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ec46f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ec46f-112">Ett `Bool` värde på eller-funktionen för predikatet som används för alla element.</span><span class="sxs-lookup"><span data-stu-id="ec46f-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ec46f-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ec46f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ec46f-114">Inte</span><span class="sxs-lookup"><span data-stu-id="ec46f-114">'T</span></span>

<span data-ttu-id="ec46f-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="ec46f-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="ec46f-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="ec46f-116">Example</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function IsThreePresent() : Bool {
    let arrayOfInts = [1, 2, 3, 4, 5];
    let is3Present = IsNumberPresentInArray(3, arrayOfInts);
    return is3Present;
}

function IsNumberPresentInArray(n : Int, array : Int[]) : Bool {
    return Any(EqualI(_, n), array);
}
```

## <a name="remarks"></a><span data-ttu-id="ec46f-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ec46f-117">Remarks</span></span>

<span data-ttu-id="ec46f-118">Funktionen definieras för generiska typer, dvs. När vi har en matris `'T[]` och en funktion `predicate: 'T -> Bool` kan vi skapa ett `Bool` värde som anger om ett element uppfyller sig `predicate` .</span><span class="sxs-lookup"><span data-stu-id="ec46f-118">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>