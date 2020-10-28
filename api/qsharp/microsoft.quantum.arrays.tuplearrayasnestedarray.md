---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: Funktionen TupleArrayAsNestedArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729974"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="f7c66-102">Funktionen TupleArrayAsNestedArray</span><span class="sxs-lookup"><span data-stu-id="f7c66-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="f7c66-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f7c66-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f7c66-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7c66-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7c66-105">Förvandlar en lista med 2-tupler till en kapslad matris.</span><span class="sxs-lookup"><span data-stu-id="f7c66-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="f7c66-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f7c66-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="f7c66-107">tupleList: (t) []</span><span class="sxs-lookup"><span data-stu-id="f7c66-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="f7c66-108">Lista över 2-tupler som ska omvandlas till en kapslad matris.</span><span class="sxs-lookup"><span data-stu-id="f7c66-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="f7c66-109">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="f7c66-109">Output : 'T[][]</span></span>

<span data-ttu-id="f7c66-110">En kapslad matris med längd som matchar tupleList.</span><span class="sxs-lookup"><span data-stu-id="f7c66-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="f7c66-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="f7c66-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="f7c66-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f7c66-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7c66-113">Inte</span><span class="sxs-lookup"><span data-stu-id="f7c66-113">'T</span></span>

