---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: Funktionen ConstantArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210071"
---
# <a name="constantarray-function"></a><span data-ttu-id="4293b-102">Funktionen ConstantArray</span><span class="sxs-lookup"><span data-stu-id="4293b-102">ConstantArray function</span></span>

<span data-ttu-id="4293b-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4293b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4293b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4293b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4293b-105">Skapar en matris med angiven längd med alla element som motsvarar det aktuella värdet.</span><span class="sxs-lookup"><span data-stu-id="4293b-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="4293b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4293b-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="4293b-107">Längd: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4293b-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4293b-108">Längden på den nya matrisen.</span><span class="sxs-lookup"><span data-stu-id="4293b-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="4293b-109">värde: ' t</span><span class="sxs-lookup"><span data-stu-id="4293b-109">value : 'T</span></span>

<span data-ttu-id="4293b-110">Värdet för varje element i den nya matrisen.</span><span class="sxs-lookup"><span data-stu-id="4293b-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="4293b-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="4293b-111">Output : 'T[]</span></span>

<span data-ttu-id="4293b-112">En ny längd mat ris `length` , t. ex. varje element `value` .</span><span class="sxs-lookup"><span data-stu-id="4293b-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4293b-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="4293b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4293b-114">Inte</span><span class="sxs-lookup"><span data-stu-id="4293b-114">'T</span></span>

