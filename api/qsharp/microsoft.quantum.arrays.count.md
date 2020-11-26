---
uid: Microsoft.Quantum.Arrays.Count
title: Funktionen Count
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 48b75cc6d6584f899223a0803f31fd174836f303
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221563"
---
# <a name="count-function"></a><span data-ttu-id="417e0-102">Funktionen Count</span><span class="sxs-lookup"><span data-stu-id="417e0-102">Count function</span></span>

<span data-ttu-id="417e0-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="417e0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="417e0-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="417e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="417e0-105">Med tanke på en matris och ett predikat som har definierats för elementen i matrisen returnerar antalet element en matris som består av de element som uppfyller predikatet.</span><span class="sxs-lookup"><span data-stu-id="417e0-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="417e0-106">Indata</span><span class="sxs-lookup"><span data-stu-id="417e0-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="417e0-107">predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="417e0-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="417e0-108">En funktion från `'T` till boolesk som används för att filtrera element.</span><span class="sxs-lookup"><span data-stu-id="417e0-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="417e0-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="417e0-109">array : 'T[]</span></span>

<span data-ttu-id="417e0-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="417e0-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="417e0-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="417e0-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="417e0-112">Antalet element i `array` som uppfyller predikatet.</span><span class="sxs-lookup"><span data-stu-id="417e0-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="417e0-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="417e0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="417e0-114">Inte</span><span class="sxs-lookup"><span data-stu-id="417e0-114">'T</span></span>

<span data-ttu-id="417e0-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="417e0-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="417e0-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="417e0-116">Remarks</span></span>

<span data-ttu-id="417e0-117">Funktionen definieras för generiska typer, d.v.s. När vi har en matris `'T[]` och ett predikat `'T -> Bool` kan vi filtrera element.</span><span class="sxs-lookup"><span data-stu-id="417e0-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>