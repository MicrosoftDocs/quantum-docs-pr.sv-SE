---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: Funktionen ConstantArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846229"
---
# <a name="constantarray-function"></a><span data-ttu-id="7d41e-102">Funktionen ConstantArray</span><span class="sxs-lookup"><span data-stu-id="7d41e-102">ConstantArray function</span></span>

<span data-ttu-id="7d41e-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7d41e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7d41e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d41e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d41e-105">Skapar en matris med angiven längd med alla element som motsvarar det aktuella värdet.</span><span class="sxs-lookup"><span data-stu-id="7d41e-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="7d41e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7d41e-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="7d41e-107">Längd: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7d41e-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7d41e-108">Längden på den nya matrisen.</span><span class="sxs-lookup"><span data-stu-id="7d41e-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="7d41e-109">värde: ' t</span><span class="sxs-lookup"><span data-stu-id="7d41e-109">value : 'T</span></span>

<span data-ttu-id="7d41e-110">Värdet för varje element i den nya matrisen.</span><span class="sxs-lookup"><span data-stu-id="7d41e-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="7d41e-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="7d41e-111">Output : 'T[]</span></span>

<span data-ttu-id="7d41e-112">En ny längd mat ris `length` , t. ex. varje element `value` .</span><span class="sxs-lookup"><span data-stu-id="7d41e-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7d41e-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="7d41e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7d41e-114">Inte</span><span class="sxs-lookup"><span data-stu-id="7d41e-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="7d41e-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="7d41e-115">Example</span></span>

<span data-ttu-id="7d41e-116">Följande kod skapar en matris med tre booleska värden, var och en som motsvarar `true` :</span><span class="sxs-lookup"><span data-stu-id="7d41e-116">The following code creates an array of 3 Boolean values, each equal to `true`:</span></span>

```qsharp
let array = ConstantArray(3, true);
```