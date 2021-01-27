---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefix funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845516"
---
# <a name="prefixes-function"></a><span data-ttu-id="8ee45-102">Prefix funktion</span><span class="sxs-lookup"><span data-stu-id="8ee45-102">Prefixes function</span></span>

<span data-ttu-id="8ee45-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8ee45-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8ee45-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ee45-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ee45-105">Med en matris returneras alla prefix.</span><span class="sxs-lookup"><span data-stu-id="8ee45-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="8ee45-106">Description</span><span class="sxs-lookup"><span data-stu-id="8ee45-106">Description</span></span>

<span data-ttu-id="8ee45-107">Returnerar en matris med alla prefix, som börjar med en matris som bara har det första elementet fram till hela matrisen.</span><span class="sxs-lookup"><span data-stu-id="8ee45-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="8ee45-108">Indata</span><span class="sxs-lookup"><span data-stu-id="8ee45-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="8ee45-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="8ee45-109">array : 'T[]</span></span>

<span data-ttu-id="8ee45-110">En matris med element.</span><span class="sxs-lookup"><span data-stu-id="8ee45-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="8ee45-111">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="8ee45-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8ee45-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8ee45-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8ee45-113">Inte</span><span class="sxs-lookup"><span data-stu-id="8ee45-113">'T</span></span>

<span data-ttu-id="8ee45-114">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="8ee45-114">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="8ee45-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="8ee45-115">Example</span></span>

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```