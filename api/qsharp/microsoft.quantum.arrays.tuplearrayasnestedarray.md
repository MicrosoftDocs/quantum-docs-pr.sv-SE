---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: Funktionen TupleArrayAsNestedArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: c898178b6385b27f753509f0748a8b666b5066bd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220084"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="50b62-102">Funktionen TupleArrayAsNestedArray</span><span class="sxs-lookup"><span data-stu-id="50b62-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="50b62-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="50b62-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="50b62-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="50b62-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="50b62-105">Förvandlar en lista med 2-tupler till en kapslad matris.</span><span class="sxs-lookup"><span data-stu-id="50b62-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="50b62-106">Indata</span><span class="sxs-lookup"><span data-stu-id="50b62-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="50b62-107">tupleList: (t) []</span><span class="sxs-lookup"><span data-stu-id="50b62-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="50b62-108">Lista över 2-tupler som ska omvandlas till en kapslad matris.</span><span class="sxs-lookup"><span data-stu-id="50b62-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="50b62-109">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="50b62-109">Output : 'T[][]</span></span>

<span data-ttu-id="50b62-110">En kapslad matris med längd som matchar tupleList.</span><span class="sxs-lookup"><span data-stu-id="50b62-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="50b62-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="50b62-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="50b62-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="50b62-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50b62-113">Inte</span><span class="sxs-lookup"><span data-stu-id="50b62-113">'T</span></span>

