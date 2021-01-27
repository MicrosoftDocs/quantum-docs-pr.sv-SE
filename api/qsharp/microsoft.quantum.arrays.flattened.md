---
uid: Microsoft.Quantum.Arrays.Flattened
title: Utplattad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 272533d4efd8598b21daa341c867c070a2083ce0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848622"
---
# <a name="flattened-function"></a><span data-ttu-id="78b86-102">Utplattad funktion</span><span class="sxs-lookup"><span data-stu-id="78b86-102">Flattened function</span></span>

<span data-ttu-id="78b86-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="78b86-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="78b86-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78b86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78b86-105">En matris med matriser returnerar sammanfogningen av alla matriser.</span><span class="sxs-lookup"><span data-stu-id="78b86-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="78b86-106">Indata</span><span class="sxs-lookup"><span data-stu-id="78b86-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="78b86-107">matriser: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="78b86-107">arrays : 'T[][]</span></span>

<span data-ttu-id="78b86-108">Matris med matriser.</span><span class="sxs-lookup"><span data-stu-id="78b86-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="78b86-109">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="78b86-109">Output : 'T[]</span></span>

<span data-ttu-id="78b86-110">Sammanfogning av alla matriser.</span><span class="sxs-lookup"><span data-stu-id="78b86-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="78b86-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="78b86-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="78b86-112">Inte</span><span class="sxs-lookup"><span data-stu-id="78b86-112">'T</span></span>

<span data-ttu-id="78b86-113">Typ av `array` element.</span><span class="sxs-lookup"><span data-stu-id="78b86-113">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="78b86-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="78b86-114">Example</span></span>

```qsharp
let flattened = Flattened([[1, 2], [3], [4, 5, 6]]);
// flattened = [1, 2, 3, 4, 5, 6]
```