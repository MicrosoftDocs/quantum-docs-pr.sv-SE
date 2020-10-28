---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefix funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730062"
---
# <a name="prefixes-function"></a><span data-ttu-id="ae43d-102">Prefix funktion</span><span class="sxs-lookup"><span data-stu-id="ae43d-102">Prefixes function</span></span>

<span data-ttu-id="ae43d-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ae43d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ae43d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae43d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae43d-105">Med en matris returneras alla prefix.</span><span class="sxs-lookup"><span data-stu-id="ae43d-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="ae43d-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ae43d-106">Description</span></span>

<span data-ttu-id="ae43d-107">Returnerar en matris med alla prefix, som börjar med en matris som bara har det första elementet fram till hela matrisen.</span><span class="sxs-lookup"><span data-stu-id="ae43d-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="ae43d-108">Indata</span><span class="sxs-lookup"><span data-stu-id="ae43d-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="ae43d-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="ae43d-109">array : 'T[]</span></span>

<span data-ttu-id="ae43d-110">En matris med element.</span><span class="sxs-lookup"><span data-stu-id="ae43d-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="ae43d-111">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="ae43d-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ae43d-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ae43d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ae43d-113">Inte</span><span class="sxs-lookup"><span data-stu-id="ae43d-113">'T</span></span>

<span data-ttu-id="ae43d-114">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="ae43d-114">The type of `array` elements.</span></span>