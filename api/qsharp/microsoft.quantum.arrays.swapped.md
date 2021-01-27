---
uid: Microsoft.Quantum.Arrays.Swapped
title: Utbytd funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850958"
---
# <a name="swapped-function"></a><span data-ttu-id="3c33d-102">Utbytd funktion</span><span class="sxs-lookup"><span data-stu-id="3c33d-102">Swapped function</span></span>

<span data-ttu-id="3c33d-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3c33d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3c33d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c33d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c33d-105">Använder en växling av två element i en matris.</span><span class="sxs-lookup"><span data-stu-id="3c33d-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="3c33d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3c33d-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="3c33d-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3c33d-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3c33d-108">Index för det första element som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="3c33d-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="3c33d-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3c33d-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3c33d-110">Index för det andra element som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="3c33d-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="3c33d-111">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="3c33d-111">arr : 'T[]</span></span>

<span data-ttu-id="3c33d-112">Matris med element som ska växlas.</span><span class="sxs-lookup"><span data-stu-id="3c33d-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="3c33d-113">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="3c33d-113">Output : 'T[]</span></span>

<span data-ttu-id="3c33d-114">Den matris som har den tillämpade växlingen på plats.</span><span class="sxs-lookup"><span data-stu-id="3c33d-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="3c33d-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="3c33d-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="3c33d-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="3c33d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3c33d-117">Inte</span><span class="sxs-lookup"><span data-stu-id="3c33d-117">'T</span></span>

