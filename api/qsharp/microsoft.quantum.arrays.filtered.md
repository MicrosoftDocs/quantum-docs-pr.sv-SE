---
uid: Microsoft.Quantum.Arrays.Filtered
title: Filtrerad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847167"
---
# <a name="filtered-function"></a><span data-ttu-id="36747-102">Filtrerad funktion</span><span class="sxs-lookup"><span data-stu-id="36747-102">Filtered function</span></span>

<span data-ttu-id="36747-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="36747-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="36747-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="36747-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="36747-105">Med tanke på en matris och ett predikat som har definierats för elementen i matrisen, returnerar en matris som består av de element som uppfyller predikatet.</span><span class="sxs-lookup"><span data-stu-id="36747-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="36747-106">Indata</span><span class="sxs-lookup"><span data-stu-id="36747-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="36747-107">predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="36747-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="36747-108">En funktion från `'T` till boolesk som används för att filtrera element.</span><span class="sxs-lookup"><span data-stu-id="36747-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="36747-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="36747-109">array : 'T[]</span></span>

<span data-ttu-id="36747-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="36747-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="36747-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="36747-111">Output : 'T[]</span></span>

<span data-ttu-id="36747-112">En matris `'T[]` med element som uppfyller predikatet.</span><span class="sxs-lookup"><span data-stu-id="36747-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="36747-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="36747-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="36747-114">Inte</span><span class="sxs-lookup"><span data-stu-id="36747-114">'T</span></span>

<span data-ttu-id="36747-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="36747-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="36747-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="36747-116">Example</span></span>

<span data-ttu-id="36747-117">Följande kod visar funktionen "filtrerad".</span><span class="sxs-lookup"><span data-stu-id="36747-117">The following code demonstrates the "Filtered" function.</span></span>
<span data-ttu-id="36747-118">Ett predikat definieras med @"microsoft.quantum.logical.greaterthani" funktionen:</span><span class="sxs-lookup"><span data-stu-id="36747-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

<span data-ttu-id="36747-119">Resultatet ett bör förvänta sig från det här exemplet är en matris med tal som är större än 5.</span><span class="sxs-lookup"><span data-stu-id="36747-119">The outcome one should expect from this example will be an array of numbers greater than 5.</span></span>

## <a name="remarks"></a><span data-ttu-id="36747-120">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="36747-120">Remarks</span></span>

<span data-ttu-id="36747-121">Funktionen definieras för generiska typer, d.v.s. När vi har en matris `'T[]` och ett predikat `'T -> Bool` kan vi filtrera element.</span><span class="sxs-lookup"><span data-stu-id="36747-121">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>