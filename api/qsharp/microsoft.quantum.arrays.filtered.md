---
uid: Microsoft.Quantum.Arrays.Filtered
title: Filtrerad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 4c786c69b0896b517f108611e32501867838aeb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730283"
---
# <a name="filtered-function"></a><span data-ttu-id="15af1-102">Filtrerad funktion</span><span class="sxs-lookup"><span data-stu-id="15af1-102">Filtered function</span></span>

<span data-ttu-id="15af1-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="15af1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="15af1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15af1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15af1-105">Med tanke på en matris och ett predikat som har definierats för elementen i matrisen, returnerar en matris som består av de element som uppfyller predikatet.</span><span class="sxs-lookup"><span data-stu-id="15af1-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="15af1-106">Indata</span><span class="sxs-lookup"><span data-stu-id="15af1-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="15af1-107">predikat: ' t-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="15af1-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="15af1-108">En funktion från `'T` till boolesk som används för att filtrera element.</span><span class="sxs-lookup"><span data-stu-id="15af1-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="15af1-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="15af1-109">array : 'T[]</span></span>

<span data-ttu-id="15af1-110">En matris med element över `'T` .</span><span class="sxs-lookup"><span data-stu-id="15af1-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="15af1-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="15af1-111">Output : 'T[]</span></span>

<span data-ttu-id="15af1-112">En matris `'T[]` med element som uppfyller predikatet.</span><span class="sxs-lookup"><span data-stu-id="15af1-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="15af1-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="15af1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="15af1-114">Inte</span><span class="sxs-lookup"><span data-stu-id="15af1-114">'T</span></span>

<span data-ttu-id="15af1-115">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="15af1-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="15af1-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="15af1-116">Remarks</span></span>

<span data-ttu-id="15af1-117">Funktionen definieras för generiska typer, d.v.s. När vi har en matris `'T[]` och ett predikat `'T -> Bool` kan vi filtrera element.</span><span class="sxs-lookup"><span data-stu-id="15af1-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>