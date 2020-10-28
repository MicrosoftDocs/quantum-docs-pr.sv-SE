---
uid: Microsoft.Quantum.Arrays.Flattened
title: Utplattad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730262"
---
# <a name="flattened-function"></a><span data-ttu-id="5365a-102">Utplattad funktion</span><span class="sxs-lookup"><span data-stu-id="5365a-102">Flattened function</span></span>

<span data-ttu-id="5365a-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5365a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5365a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5365a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5365a-105">En matris med matriser returnerar sammanfogningen av alla matriser.</span><span class="sxs-lookup"><span data-stu-id="5365a-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="5365a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5365a-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="5365a-107">matriser: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="5365a-107">arrays : 'T[][]</span></span>

<span data-ttu-id="5365a-108">Matris med matriser.</span><span class="sxs-lookup"><span data-stu-id="5365a-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="5365a-109">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="5365a-109">Output : 'T[]</span></span>

<span data-ttu-id="5365a-110">Sammanfogning av alla matriser.</span><span class="sxs-lookup"><span data-stu-id="5365a-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5365a-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="5365a-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5365a-112">Inte</span><span class="sxs-lookup"><span data-stu-id="5365a-112">'T</span></span>

<span data-ttu-id="5365a-113">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="5365a-113">The type of `array` elements.</span></span>