---
uid: Microsoft.Quantum.Arrays.Any
title: Alla funktioner
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: dd5639f1b0a76cb356c89aca0c0e02d375f30d12
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730419"
---
# <a name="any-function"></a><span data-ttu-id="77661-102">Alla funktioner</span><span class="sxs-lookup"><span data-stu-id="77661-102">Any function</span></span>

<span data-ttu-id="77661-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="77661-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="77661-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="77661-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="77661-105">Med en matris och ett predikat som har definierats för elementen i matrisen, kontrollerar om minst ett element i matrisen uppfyller predikatet.</span><span class="sxs-lookup"><span data-stu-id="77661-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="77661-106">Indata</span><span class="sxs-lookup"><span data-stu-id="77661-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="77661-107">predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="77661-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="77661-108">En funktion från `'T` till `Bool` som används för att kontrol lera element.</span><span class="sxs-lookup"><span data-stu-id="77661-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="77661-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="77661-109">array : 'T[]</span></span>

<span data-ttu-id="77661-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="77661-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="77661-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="77661-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="77661-112">Ett `Bool` värde på eller-funktionen för predikatet som används för alla element.</span><span class="sxs-lookup"><span data-stu-id="77661-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="77661-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="77661-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="77661-114">Inte</span><span class="sxs-lookup"><span data-stu-id="77661-114">'T</span></span>

<span data-ttu-id="77661-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="77661-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="77661-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="77661-116">Remarks</span></span>

<span data-ttu-id="77661-117">Funktionen definieras för generiska typer, dvs. När vi har en matris `'T[]` och en funktion `predicate: 'T -> Bool` kan vi skapa ett `Bool` värde som anger om ett element uppfyller sig `predicate` .</span><span class="sxs-lookup"><span data-stu-id="77661-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>