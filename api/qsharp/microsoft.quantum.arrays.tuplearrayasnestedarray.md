---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: Funktionen TupleArrayAsNestedArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 51a35555080d1d2475fc1aa9e48e84c7c6f92c51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845399"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="e5149-102">Funktionen TupleArrayAsNestedArray</span><span class="sxs-lookup"><span data-stu-id="e5149-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="e5149-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e5149-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e5149-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5149-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5149-105">Förvandlar en lista med 2-tupler till en kapslad matris.</span><span class="sxs-lookup"><span data-stu-id="e5149-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="e5149-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e5149-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="e5149-107">tupleList: (t) []</span><span class="sxs-lookup"><span data-stu-id="e5149-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="e5149-108">Lista över 2-tupler som ska omvandlas till en kapslad matris.</span><span class="sxs-lookup"><span data-stu-id="e5149-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="e5149-109">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="e5149-109">Output : 'T[][]</span></span>

<span data-ttu-id="e5149-110">En kapslad matris med längd som matchar tupleList.</span><span class="sxs-lookup"><span data-stu-id="e5149-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="e5149-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="e5149-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="e5149-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="e5149-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e5149-113">Inte</span><span class="sxs-lookup"><span data-stu-id="e5149-113">'T</span></span>

