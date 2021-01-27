---
uid: Microsoft.Quantum.Canon.Compose
title: Funktionen Skriv
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840914"
---
# <a name="compose-function"></a><span data-ttu-id="88210-102">Funktionen Skriv</span><span class="sxs-lookup"><span data-stu-id="88210-102">Compose function</span></span>

<span data-ttu-id="88210-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="88210-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="88210-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88210-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88210-105">Returnerar sammansättningen för två functions.</span><span class="sxs-lookup"><span data-stu-id="88210-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="88210-106">Description</span><span class="sxs-lookup"><span data-stu-id="88210-106">Description</span></span>

<span data-ttu-id="88210-107">Två Functions $f $ och $g $ returnerar en ny funktion som representerar $f \circ g $.</span><span class="sxs-lookup"><span data-stu-id="88210-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="88210-108">Indata</span><span class="sxs-lookup"><span data-stu-id="88210-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="88210-109">yttre: "U->" V</span><span class="sxs-lookup"><span data-stu-id="88210-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="88210-110">Den andra funktionen som ska användas.</span><span class="sxs-lookup"><span data-stu-id="88210-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="88210-111">inre: ' t-> ' U</span><span class="sxs-lookup"><span data-stu-id="88210-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="88210-112">Den första funktionen som ska användas.</span><span class="sxs-lookup"><span data-stu-id="88210-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="88210-113">Utdata: ' t-> ' V</span><span class="sxs-lookup"><span data-stu-id="88210-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="88210-114">En ny funktion $h $ t. ex. för alla indata $x $, $f (g (x)) = h (x) $.</span><span class="sxs-lookup"><span data-stu-id="88210-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="88210-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="88210-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="88210-116">Inte</span><span class="sxs-lookup"><span data-stu-id="88210-116">'T</span></span>

<span data-ttu-id="88210-117">Indatatypen för den första funktionen som ska användas.</span><span class="sxs-lookup"><span data-stu-id="88210-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="88210-118">' U</span><span class="sxs-lookup"><span data-stu-id="88210-118">'U</span></span>

<span data-ttu-id="88210-119">Utdatatypen för den första funktionen som ska användas och indatatypen för den andra funktionen som ska användas.</span><span class="sxs-lookup"><span data-stu-id="88210-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="88210-120">' V</span><span class="sxs-lookup"><span data-stu-id="88210-120">'V</span></span>

<span data-ttu-id="88210-121">Utdatatypen för den andra funktionen som ska användas.</span><span class="sxs-lookup"><span data-stu-id="88210-121">The output type of the second function to be applied.</span></span>