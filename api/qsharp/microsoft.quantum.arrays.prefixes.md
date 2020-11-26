---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefix funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220404"
---
# <a name="prefixes-function"></a><span data-ttu-id="98f3f-102">Prefix funktion</span><span class="sxs-lookup"><span data-stu-id="98f3f-102">Prefixes function</span></span>

<span data-ttu-id="98f3f-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="98f3f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="98f3f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98f3f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98f3f-105">Med en matris returneras alla prefix.</span><span class="sxs-lookup"><span data-stu-id="98f3f-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="98f3f-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="98f3f-106">Description</span></span>

<span data-ttu-id="98f3f-107">Returnerar en matris med alla prefix, som börjar med en matris som bara har det första elementet fram till hela matrisen.</span><span class="sxs-lookup"><span data-stu-id="98f3f-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="98f3f-108">Indata</span><span class="sxs-lookup"><span data-stu-id="98f3f-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="98f3f-109">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="98f3f-109">array : 'T[]</span></span>

<span data-ttu-id="98f3f-110">En matris med element.</span><span class="sxs-lookup"><span data-stu-id="98f3f-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="98f3f-111">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="98f3f-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="98f3f-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="98f3f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="98f3f-113">Inte</span><span class="sxs-lookup"><span data-stu-id="98f3f-113">'T</span></span>

<span data-ttu-id="98f3f-114">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="98f3f-114">The type of `array` elements.</span></span>