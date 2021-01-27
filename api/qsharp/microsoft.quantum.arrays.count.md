---
uid: Microsoft.Quantum.Arrays.Count
title: Funktionen Count
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842841"
---
# <a name="count-function"></a><span data-ttu-id="edc66-102">Funktionen Count</span><span class="sxs-lookup"><span data-stu-id="edc66-102">Count function</span></span>

<span data-ttu-id="edc66-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="edc66-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="edc66-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="edc66-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="edc66-105">Med tanke på en matris och ett predikat som har definierats för elementen i matrisen returnerar antalet element en matris som består av de element som uppfyller predikatet.</span><span class="sxs-lookup"><span data-stu-id="edc66-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="edc66-106">Indata</span><span class="sxs-lookup"><span data-stu-id="edc66-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="edc66-107">predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="edc66-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="edc66-108">En funktion från `'T` till boolesk som används för att filtrera element.</span><span class="sxs-lookup"><span data-stu-id="edc66-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="edc66-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="edc66-109">array : 'T[]</span></span>

<span data-ttu-id="edc66-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="edc66-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="edc66-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="edc66-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="edc66-112">Antalet element i `array` som uppfyller predikatet.</span><span class="sxs-lookup"><span data-stu-id="edc66-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="edc66-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="edc66-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="edc66-114">Inte</span><span class="sxs-lookup"><span data-stu-id="edc66-114">'T</span></span>

<span data-ttu-id="edc66-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="edc66-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="edc66-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="edc66-116">Example</span></span>

<span data-ttu-id="edc66-117">Följande kod visar funktionen "count".</span><span class="sxs-lookup"><span data-stu-id="edc66-117">The following code demonstrates the "Count" function.</span></span>
<span data-ttu-id="edc66-118">Ett predikat definieras med @"microsoft.quantum.logical.greaterthani" funktionen:</span><span class="sxs-lookup"><span data-stu-id="edc66-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a><span data-ttu-id="edc66-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="edc66-119">Remarks</span></span>

<span data-ttu-id="edc66-120">Funktionen definieras för generiska typer, d.v.s. När vi har en matris `'T[]` och ett predikat `'T -> Bool` kan vi filtrera element.</span><span class="sxs-lookup"><span data-stu-id="edc66-120">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>