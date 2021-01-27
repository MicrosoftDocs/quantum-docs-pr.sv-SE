---
uid: Microsoft.Quantum.Arrays.Padded
title: Utfylld funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845570"
---
# <a name="padded-function"></a><span data-ttu-id="1acfd-102">Utfylld funktion</span><span class="sxs-lookup"><span data-stu-id="1acfd-102">Padded function</span></span>

<span data-ttu-id="1acfd-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1acfd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1acfd-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1acfd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1acfd-105">Returnerar en matris som är utfyllnadad vid med angivna värden upp till en angiven längd.</span><span class="sxs-lookup"><span data-stu-id="1acfd-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="1acfd-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1acfd-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="1acfd-107">nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1acfd-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1acfd-108">Längden på den utfyllda matrisen.</span><span class="sxs-lookup"><span data-stu-id="1acfd-108">The length of the padded array.</span></span> <span data-ttu-id="1acfd-109">Om detta är positivt `inputArray` fylls huvudet i på huvudet.</span><span class="sxs-lookup"><span data-stu-id="1acfd-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="1acfd-110">Om detta är negativt `inputArray` fylls det i på slutet.</span><span class="sxs-lookup"><span data-stu-id="1acfd-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="1acfd-111">defaultElement: ' t</span><span class="sxs-lookup"><span data-stu-id="1acfd-111">defaultElement : 'T</span></span>

<span data-ttu-id="1acfd-112">Standardvärde som ska användas för fyllnads element.</span><span class="sxs-lookup"><span data-stu-id="1acfd-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="1acfd-113">inputArray: inte []</span><span class="sxs-lookup"><span data-stu-id="1acfd-113">inputArray : 'T[]</span></span>

<span data-ttu-id="1acfd-114">Matris vars värden finns i huvudet i den utgående matrisen.</span><span class="sxs-lookup"><span data-stu-id="1acfd-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="1acfd-115">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="1acfd-115">Output : 'T[]</span></span>

<span data-ttu-id="1acfd-116">En matris `output` som är `inputArray` utfylld i huvudet med `defaultElement` s fram till `output` längden `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="1acfd-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1acfd-117">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="1acfd-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1acfd-118">Inte</span><span class="sxs-lookup"><span data-stu-id="1acfd-118">'T</span></span>

<span data-ttu-id="1acfd-119">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="1acfd-119">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="1acfd-120">Exempel</span><span class="sxs-lookup"><span data-stu-id="1acfd-120">Example</span></span>

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```