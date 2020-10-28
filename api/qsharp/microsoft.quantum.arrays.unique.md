---
uid: Microsoft.Quantum.Arrays.Unique
title: Unik funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: c5d40bb82f2de640e9c78eef0c27e4766b477826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729958"
---
# <a name="unique-function"></a><span data-ttu-id="298e4-102">Unik funktion</span><span class="sxs-lookup"><span data-stu-id="298e4-102">Unique function</span></span>

<span data-ttu-id="298e4-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="298e4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="298e4-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="298e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="298e4-105">Returnerar en ny matris som inte har lika intilliggande element.</span><span class="sxs-lookup"><span data-stu-id="298e4-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="298e4-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="298e4-106">Description</span></span>

<span data-ttu-id="298e4-107">Funktionen returnerar en matris med element och en funktion för att testa likheten. den här funktionen returnerar en ny matris där den relativa ordningen på elementen behålls, men alla intilliggande element som är lika med filtreras till bara ett enda element.</span><span class="sxs-lookup"><span data-stu-id="298e4-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="298e4-108">Indata</span><span class="sxs-lookup"><span data-stu-id="298e4-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="298e4-109">lika med: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="298e4-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="298e4-110">En funktion som jämför två element som `a` anses vara lika med `b` om `equal(a, b)` är `true` .</span><span class="sxs-lookup"><span data-stu-id="298e4-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="298e4-111">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="298e4-111">array : 'T[]</span></span>

<span data-ttu-id="298e4-112">Matrisen som ska filtreras för unika element.</span><span class="sxs-lookup"><span data-stu-id="298e4-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="298e4-113">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="298e4-113">Output : 'T[]</span></span>

<span data-ttu-id="298e4-114">Matris utan lika intilliggande element.</span><span class="sxs-lookup"><span data-stu-id="298e4-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="298e4-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="298e4-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="298e4-116">Inte</span><span class="sxs-lookup"><span data-stu-id="298e4-116">'T</span></span>

<span data-ttu-id="298e4-117">Typen för varje element i `array` .</span><span class="sxs-lookup"><span data-stu-id="298e4-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="298e4-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="298e4-118">Remarks</span></span>

<span data-ttu-id="298e4-119">Om det finns flera element som är identiska men inte bredvid varandra, kommer det att finnas flera förekomster i den utgående matrisen.</span><span class="sxs-lookup"><span data-stu-id="298e4-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="298e4-120">Använd den här funktionen tillsammans med `Sorted` för att hämta en matris med övergripande unika element.</span><span class="sxs-lookup"><span data-stu-id="298e4-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>