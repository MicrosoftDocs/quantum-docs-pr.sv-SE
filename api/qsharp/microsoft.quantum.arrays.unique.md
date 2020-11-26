---
uid: Microsoft.Quantum.Arrays.Unique
title: Unik funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220016"
---
# <a name="unique-function"></a><span data-ttu-id="2224c-102">Unik funktion</span><span class="sxs-lookup"><span data-stu-id="2224c-102">Unique function</span></span>

<span data-ttu-id="2224c-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2224c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2224c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2224c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2224c-105">Returnerar en ny matris som inte har lika intilliggande element.</span><span class="sxs-lookup"><span data-stu-id="2224c-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="2224c-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2224c-106">Description</span></span>

<span data-ttu-id="2224c-107">Funktionen returnerar en matris med element och en funktion för att testa likheten. den här funktionen returnerar en ny matris där den relativa ordningen på elementen behålls, men alla intilliggande element som är lika med filtreras till bara ett enda element.</span><span class="sxs-lookup"><span data-stu-id="2224c-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="2224c-108">Indata</span><span class="sxs-lookup"><span data-stu-id="2224c-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="2224c-109">lika med: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2224c-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2224c-110">En funktion som jämför två element som `a` anses vara lika med `b` om `equal(a, b)` är `true` .</span><span class="sxs-lookup"><span data-stu-id="2224c-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="2224c-111">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="2224c-111">array : 'T[]</span></span>

<span data-ttu-id="2224c-112">Matrisen som ska filtreras för unika element.</span><span class="sxs-lookup"><span data-stu-id="2224c-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="2224c-113">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="2224c-113">Output : 'T[]</span></span>

<span data-ttu-id="2224c-114">Matris utan lika intilliggande element.</span><span class="sxs-lookup"><span data-stu-id="2224c-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2224c-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="2224c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2224c-116">Inte</span><span class="sxs-lookup"><span data-stu-id="2224c-116">'T</span></span>

<span data-ttu-id="2224c-117">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="2224c-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2224c-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="2224c-118">Remarks</span></span>

<span data-ttu-id="2224c-119">Om det finns flera element som är identiska men inte bredvid varandra, kommer det att finnas flera förekomster i den utgående matrisen.</span><span class="sxs-lookup"><span data-stu-id="2224c-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="2224c-120">Använd den här funktionen tillsammans med `Sorted` för att hämta en matris med övergripande unika element.</span><span class="sxs-lookup"><span data-stu-id="2224c-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>