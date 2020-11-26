---
uid: Microsoft.Quantum.Arrays.Padded
title: Utfylld funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 2b7a80d1cf5c82a1ff52bc4aa207cfe335b40061
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220543"
---
# <a name="padded-function"></a><span data-ttu-id="aa4f0-102">Utfylld funktion</span><span class="sxs-lookup"><span data-stu-id="aa4f0-102">Padded function</span></span>

<span data-ttu-id="aa4f0-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="aa4f0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="aa4f0-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa4f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa4f0-105">Returnerar en matris som är utfyllnadad vid med angivna värden upp till en angiven längd.</span><span class="sxs-lookup"><span data-stu-id="aa4f0-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="aa4f0-106">Indata</span><span class="sxs-lookup"><span data-stu-id="aa4f0-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="aa4f0-107">nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aa4f0-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aa4f0-108">Längden på den utfyllda matrisen.</span><span class="sxs-lookup"><span data-stu-id="aa4f0-108">The length of the padded array.</span></span> <span data-ttu-id="aa4f0-109">Om detta är positivt `inputArray` fylls huvudet i på huvudet.</span><span class="sxs-lookup"><span data-stu-id="aa4f0-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="aa4f0-110">Om detta är negativt `inputArray` fylls det i på slutet.</span><span class="sxs-lookup"><span data-stu-id="aa4f0-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="aa4f0-111">defaultElement: ' t</span><span class="sxs-lookup"><span data-stu-id="aa4f0-111">defaultElement : 'T</span></span>

<span data-ttu-id="aa4f0-112">Standardvärde som ska användas för fyllnads element.</span><span class="sxs-lookup"><span data-stu-id="aa4f0-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="aa4f0-113">inputArray: inte []</span><span class="sxs-lookup"><span data-stu-id="aa4f0-113">inputArray : 'T[]</span></span>

<span data-ttu-id="aa4f0-114">Matris vars värden finns i huvudet i den utgående matrisen.</span><span class="sxs-lookup"><span data-stu-id="aa4f0-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="aa4f0-115">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="aa4f0-115">Output : 'T[]</span></span>

<span data-ttu-id="aa4f0-116">En matris `output` som är `inputArray` utfylld i huvudet med `defaultElement` s fram till `output` längden `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="aa4f0-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="aa4f0-117">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="aa4f0-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aa4f0-118">Inte</span><span class="sxs-lookup"><span data-stu-id="aa4f0-118">'T</span></span>

<span data-ttu-id="aa4f0-119">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="aa4f0-119">The type of the array elements.</span></span>