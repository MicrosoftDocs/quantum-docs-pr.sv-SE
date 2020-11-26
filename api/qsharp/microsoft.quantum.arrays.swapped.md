---
uid: Microsoft.Quantum.Arrays.Swapped
title: Utbytd funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 173fb32b5a41ce054f19548a7fcca18c11c4c4cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220135"
---
# <a name="swapped-function"></a><span data-ttu-id="e7f0b-102">Utbytd funktion</span><span class="sxs-lookup"><span data-stu-id="e7f0b-102">Swapped function</span></span>

<span data-ttu-id="e7f0b-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e7f0b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e7f0b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7f0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7f0b-105">Använder en växling av två element i en matris.</span><span class="sxs-lookup"><span data-stu-id="e7f0b-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e7f0b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e7f0b-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="e7f0b-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7f0b-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e7f0b-108">Index för det första element som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="e7f0b-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="e7f0b-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e7f0b-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e7f0b-110">Index för det andra element som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="e7f0b-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="e7f0b-111">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="e7f0b-111">arr : 'T[]</span></span>

<span data-ttu-id="e7f0b-112">Matris med element som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="e7f0b-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="e7f0b-113">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="e7f0b-113">Output : 'T[]</span></span>

<span data-ttu-id="e7f0b-114">Den matris som har den tillämpade växlingen på plats.</span><span class="sxs-lookup"><span data-stu-id="e7f0b-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="e7f0b-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="e7f0b-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="e7f0b-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="e7f0b-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e7f0b-117">Inte</span><span class="sxs-lookup"><span data-stu-id="e7f0b-117">'T</span></span>

