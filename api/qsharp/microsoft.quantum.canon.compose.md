---
uid: Microsoft.Quantum.Canon.Compose
title: Funktionen Skriv
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728839"
---
# <a name="compose-function"></a><span data-ttu-id="c1740-102">Funktionen Skriv</span><span class="sxs-lookup"><span data-stu-id="c1740-102">Compose function</span></span>

<span data-ttu-id="c1740-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c1740-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c1740-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c1740-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c1740-105">Returnerar sammansättningen för två functions.</span><span class="sxs-lookup"><span data-stu-id="c1740-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="c1740-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c1740-106">Description</span></span>

<span data-ttu-id="c1740-107">Två Functions $f $ och $g $ returnerar en ny funktion som representerar $f \circ g $.</span><span class="sxs-lookup"><span data-stu-id="c1740-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="c1740-108">Indata</span><span class="sxs-lookup"><span data-stu-id="c1740-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="c1740-109">yttre: "U->" V</span><span class="sxs-lookup"><span data-stu-id="c1740-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="c1740-110">Den andra funktionen som ska användas.</span><span class="sxs-lookup"><span data-stu-id="c1740-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="c1740-111">inre: ' t-> ' U</span><span class="sxs-lookup"><span data-stu-id="c1740-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="c1740-112">Den första funktionen som ska användas.</span><span class="sxs-lookup"><span data-stu-id="c1740-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="c1740-113">Utdata: ' t-> ' V</span><span class="sxs-lookup"><span data-stu-id="c1740-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="c1740-114">En ny funktion $h $ t. ex. för alla indata $x $, $f (g (x)) = h (x) $.</span><span class="sxs-lookup"><span data-stu-id="c1740-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c1740-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="c1740-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c1740-116">Inte</span><span class="sxs-lookup"><span data-stu-id="c1740-116">'T</span></span>

<span data-ttu-id="c1740-117">Indatatypen för den första funktionen som ska användas.</span><span class="sxs-lookup"><span data-stu-id="c1740-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="c1740-118">' U</span><span class="sxs-lookup"><span data-stu-id="c1740-118">'U</span></span>

<span data-ttu-id="c1740-119">Utdatatypen för den första funktionen som ska användas och indatatypen för den andra funktionen som ska användas.</span><span class="sxs-lookup"><span data-stu-id="c1740-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="c1740-120">' V</span><span class="sxs-lookup"><span data-stu-id="c1740-120">'V</span></span>

<span data-ttu-id="c1740-121">Utdatatypen för den andra funktionen som ska användas.</span><span class="sxs-lookup"><span data-stu-id="c1740-121">The output type of the second function to be applied.</span></span>