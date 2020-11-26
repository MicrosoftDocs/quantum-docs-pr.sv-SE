---
uid: Microsoft.Quantum.Arrays.Flattened
title: Utplattad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221223"
---
# <a name="flattened-function"></a><span data-ttu-id="ffbe8-102">Utplattad funktion</span><span class="sxs-lookup"><span data-stu-id="ffbe8-102">Flattened function</span></span>

<span data-ttu-id="ffbe8-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ffbe8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ffbe8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ffbe8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ffbe8-105">En matris med matriser returnerar sammanfogningen av alla matriser.</span><span class="sxs-lookup"><span data-stu-id="ffbe8-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ffbe8-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ffbe8-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="ffbe8-107">matriser: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="ffbe8-107">arrays : 'T[][]</span></span>

<span data-ttu-id="ffbe8-108">Matris med matriser.</span><span class="sxs-lookup"><span data-stu-id="ffbe8-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="ffbe8-109">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="ffbe8-109">Output : 'T[]</span></span>

<span data-ttu-id="ffbe8-110">Sammanfogning av alla matriser.</span><span class="sxs-lookup"><span data-stu-id="ffbe8-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ffbe8-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="ffbe8-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ffbe8-112">Inte</span><span class="sxs-lookup"><span data-stu-id="ffbe8-112">'T</span></span>

<span data-ttu-id="ffbe8-113">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="ffbe8-113">The type of `array` elements.</span></span>