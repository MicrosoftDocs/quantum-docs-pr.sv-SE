---
uid: Microsoft.Quantum.Arrays.Fold
title: Viknings funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730243"
---
# <a name="fold-function"></a><span data-ttu-id="94451-102">Viknings funktion</span><span class="sxs-lookup"><span data-stu-id="94451-102">Fold function</span></span>

<span data-ttu-id="94451-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="94451-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="94451-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94451-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94451-105">Itererar en funktion `f` genom en matris `array` och returnerar `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="94451-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="94451-106">Indata</span><span class="sxs-lookup"><span data-stu-id="94451-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="94451-107">mapp: (' State, s)-> ' status</span><span class="sxs-lookup"><span data-stu-id="94451-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="94451-108">En funktion som ska vikas över matrisen.</span><span class="sxs-lookup"><span data-stu-id="94451-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="94451-109">tillstånd: status</span><span class="sxs-lookup"><span data-stu-id="94451-109">state : 'State</span></span>

<span data-ttu-id="94451-110">Mappens initiala tillstånd.</span><span class="sxs-lookup"><span data-stu-id="94451-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="94451-111">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="94451-111">array : 'T[]</span></span>

<span data-ttu-id="94451-112">En matris med värden som ska vikas över.</span><span class="sxs-lookup"><span data-stu-id="94451-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="94451-113">Utdata: status</span><span class="sxs-lookup"><span data-stu-id="94451-113">Output : 'State</span></span>

<span data-ttu-id="94451-114">Det slutliga tillstånd som returneras av mappen efter att du har itererat över alla element i `array` .</span><span class="sxs-lookup"><span data-stu-id="94451-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="94451-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="94451-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="94451-116">Status</span><span class="sxs-lookup"><span data-stu-id="94451-116">'State</span></span>

<span data-ttu-id="94451-117">Den typ av tillstånd `folder` som funktionen körs på, dvs accepterar som första argument och returnerar.</span><span class="sxs-lookup"><span data-stu-id="94451-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="94451-118">Inte</span><span class="sxs-lookup"><span data-stu-id="94451-118">'T</span></span>

<span data-ttu-id="94451-119">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="94451-119">The type of `array` elements.</span></span>