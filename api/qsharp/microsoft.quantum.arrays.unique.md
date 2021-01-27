---
uid: Microsoft.Quantum.Arrays.Unique
title: Unik funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850910"
---
# <a name="unique-function"></a><span data-ttu-id="6f700-102">Unik funktion</span><span class="sxs-lookup"><span data-stu-id="6f700-102">Unique function</span></span>

<span data-ttu-id="6f700-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6f700-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6f700-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f700-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f700-105">Returnerar en ny matris som inte har lika intilliggande element.</span><span class="sxs-lookup"><span data-stu-id="6f700-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="6f700-106">Description</span><span class="sxs-lookup"><span data-stu-id="6f700-106">Description</span></span>

<span data-ttu-id="6f700-107">Funktionen returnerar en matris med element och en funktion för att testa likheten. den här funktionen returnerar en ny matris där den relativa ordningen på elementen behålls, men alla intilliggande element som är lika med filtreras till bara ett enda element.</span><span class="sxs-lookup"><span data-stu-id="6f700-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="6f700-108">Indata</span><span class="sxs-lookup"><span data-stu-id="6f700-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="6f700-109">lika med: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6f700-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6f700-110">En funktion som jämför två element som `a` anses vara lika med `b` om `equal(a, b)` är `true` .</span><span class="sxs-lookup"><span data-stu-id="6f700-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="6f700-111">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="6f700-111">array : 'T[]</span></span>

<span data-ttu-id="6f700-112">Matrisen som ska filtreras för unika element.</span><span class="sxs-lookup"><span data-stu-id="6f700-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="6f700-113">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="6f700-113">Output : 'T[]</span></span>

<span data-ttu-id="6f700-114">Matris utan lika intilliggande element.</span><span class="sxs-lookup"><span data-stu-id="6f700-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6f700-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="6f700-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6f700-116">Inte</span><span class="sxs-lookup"><span data-stu-id="6f700-116">'T</span></span>

<span data-ttu-id="6f700-117">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="6f700-117">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="6f700-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="6f700-118">Example</span></span>

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a><span data-ttu-id="6f700-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6f700-119">Remarks</span></span>

<span data-ttu-id="6f700-120">Om det finns flera element som är identiska men inte bredvid varandra, kommer det att finnas flera förekomster i den utgående matrisen.</span><span class="sxs-lookup"><span data-stu-id="6f700-120">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="6f700-121">Använd den här funktionen tillsammans med `Sorted` för att hämta en matris med övergripande unika element.</span><span class="sxs-lookup"><span data-stu-id="6f700-121">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>