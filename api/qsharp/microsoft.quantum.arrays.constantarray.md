---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: Funktionen ConstantArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730379"
---
# <a name="constantarray-function"></a><span data-ttu-id="4a6b4-102">Funktionen ConstantArray</span><span class="sxs-lookup"><span data-stu-id="4a6b4-102">ConstantArray function</span></span>

<span data-ttu-id="4a6b4-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4a6b4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4a6b4-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4a6b4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4a6b4-105">Skapar en matris med angiven längd med alla element som motsvarar det aktuella värdet.</span><span class="sxs-lookup"><span data-stu-id="4a6b4-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="4a6b4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4a6b4-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="4a6b4-107">Längd: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4a6b4-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4a6b4-108">Längden på den nya matrisen.</span><span class="sxs-lookup"><span data-stu-id="4a6b4-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="4a6b4-109">värde: ' t</span><span class="sxs-lookup"><span data-stu-id="4a6b4-109">value : 'T</span></span>

<span data-ttu-id="4a6b4-110">Värdet för varje element i den nya matrisen.</span><span class="sxs-lookup"><span data-stu-id="4a6b4-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="4a6b4-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="4a6b4-111">Output : 'T[]</span></span>

<span data-ttu-id="4a6b4-112">En ny längd mat ris `length` , t. ex. varje element `value` .</span><span class="sxs-lookup"><span data-stu-id="4a6b4-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4a6b4-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="4a6b4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4a6b4-114">Inte</span><span class="sxs-lookup"><span data-stu-id="4a6b4-114">'T</span></span>

