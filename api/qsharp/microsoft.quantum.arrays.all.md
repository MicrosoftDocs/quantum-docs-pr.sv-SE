---
uid: Microsoft.Quantum.Arrays.All
title: All-funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 345c3fb92babd4ae2e54803b6c3b79b3313ef417
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730422"
---
# <a name="all-function"></a><span data-ttu-id="5ee0e-102">All-funktion</span><span class="sxs-lookup"><span data-stu-id="5ee0e-102">All function</span></span>

<span data-ttu-id="5ee0e-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5ee0e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5ee0e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5ee0e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5ee0e-105">Tilldelas en matris och ett predikat som har definierats för elementen i matrisen och kontrollerar om alla element i matrisen uppfyller predikatet.</span><span class="sxs-lookup"><span data-stu-id="5ee0e-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="5ee0e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5ee0e-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="5ee0e-107">predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5ee0e-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5ee0e-108">En funktion från `'T` till `Bool` som används för att kontrol lera element.</span><span class="sxs-lookup"><span data-stu-id="5ee0e-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="5ee0e-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="5ee0e-109">array : 'T[]</span></span>

<span data-ttu-id="5ee0e-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="5ee0e-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5ee0e-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5ee0e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5ee0e-112">Ett `Bool` värde på-och-funktionen för predikatet som används för alla element.</span><span class="sxs-lookup"><span data-stu-id="5ee0e-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5ee0e-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="5ee0e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5ee0e-114">Inte</span><span class="sxs-lookup"><span data-stu-id="5ee0e-114">'T</span></span>

<span data-ttu-id="5ee0e-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="5ee0e-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ee0e-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5ee0e-116">Remarks</span></span>

<span data-ttu-id="5ee0e-117">Funktionen definieras för generiska typer, d.v.s. När vi har en matris `'T[]` och en funktion `predicate: 'T -> Bool` kan vi skapa ett `Bool` värde som anger om alla element uppfyller `predicate` .</span><span class="sxs-lookup"><span data-stu-id="5ee0e-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>