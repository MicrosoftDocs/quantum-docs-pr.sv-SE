---
uid: Microsoft.Quantum.Arrays.Fold
title: Viknings funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848612"
---
# <a name="fold-function"></a><span data-ttu-id="ac651-102">Viknings funktion</span><span class="sxs-lookup"><span data-stu-id="ac651-102">Fold function</span></span>

<span data-ttu-id="ac651-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ac651-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ac651-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac651-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac651-105">Itererar en funktion `f` genom en matris `array` och returnerar `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="ac651-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="ac651-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ac651-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="ac651-107">mapp: (' State, s)-> ' status</span><span class="sxs-lookup"><span data-stu-id="ac651-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="ac651-108">En funktion som ska vikas över matrisen.</span><span class="sxs-lookup"><span data-stu-id="ac651-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="ac651-109">tillstånd: status</span><span class="sxs-lookup"><span data-stu-id="ac651-109">state : 'State</span></span>

<span data-ttu-id="ac651-110">Mappens initiala tillstånd.</span><span class="sxs-lookup"><span data-stu-id="ac651-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="ac651-111">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="ac651-111">array : 'T[]</span></span>

<span data-ttu-id="ac651-112">En matris med värden som ska vikas över.</span><span class="sxs-lookup"><span data-stu-id="ac651-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="ac651-113">Utdata: status</span><span class="sxs-lookup"><span data-stu-id="ac651-113">Output : 'State</span></span>

<span data-ttu-id="ac651-114">Det slutliga tillstånd som returneras av mappen efter att du har itererat över alla element i `array` .</span><span class="sxs-lookup"><span data-stu-id="ac651-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ac651-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ac651-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="ac651-116">Status</span><span class="sxs-lookup"><span data-stu-id="ac651-116">'State</span></span>

<span data-ttu-id="ac651-117">Den typ av tillstånd `folder` som funktionen körs på, dvs accepterar som första argument och returnerar.</span><span class="sxs-lookup"><span data-stu-id="ac651-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="ac651-118">Inte</span><span class="sxs-lookup"><span data-stu-id="ac651-118">'T</span></span>

<span data-ttu-id="ac651-119">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="ac651-119">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="ac651-120">Exempel</span><span class="sxs-lookup"><span data-stu-id="ac651-120">Example</span></span>

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```