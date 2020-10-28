---
uid: Microsoft.Quantum.Arrays.Transposed
title: Transponerad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729979"
---
# <a name="transposed-function"></a><span data-ttu-id="2ef09-102">Transponerad funktion</span><span class="sxs-lookup"><span data-stu-id="2ef09-102">Transposed function</span></span>

<span data-ttu-id="2ef09-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2ef09-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2ef09-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2ef09-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2ef09-105">Returnerar Transponeringen av en matris som visas som en matris med matriser.</span><span class="sxs-lookup"><span data-stu-id="2ef09-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="2ef09-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2ef09-106">Description</span></span>

<span data-ttu-id="2ef09-107">Mata in som en $r \times c $-matris med $r $ rader och $c $ columns.</span><span class="sxs-lookup"><span data-stu-id="2ef09-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="2ef09-108">Matrisen är rad-baserad, d.v.s. kommer att `matrix[i][j]` få åtkomst till elementet på rad $i $ och kolumn $j $.</span><span class="sxs-lookup"><span data-stu-id="2ef09-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="2ef09-109">Den här funktionen returnerar den $c \times r $-matrisen som är transponerad för den angivna matrisen.</span><span class="sxs-lookup"><span data-stu-id="2ef09-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="2ef09-110">Indata</span><span class="sxs-lookup"><span data-stu-id="2ef09-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="2ef09-111">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="2ef09-111">matrix : 'T[][]</span></span>

<span data-ttu-id="2ef09-112">Rad-baserad $r \times c $ Matrix</span><span class="sxs-lookup"><span data-stu-id="2ef09-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="2ef09-113">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="2ef09-113">Output : 'T[][]</span></span>

<span data-ttu-id="2ef09-114">Transponerad $c \times r $ Matrix</span><span class="sxs-lookup"><span data-stu-id="2ef09-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2ef09-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="2ef09-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2ef09-116">Inte</span><span class="sxs-lookup"><span data-stu-id="2ef09-116">'T</span></span>

<span data-ttu-id="2ef09-117">Typen för varje element i `matrix` .</span><span class="sxs-lookup"><span data-stu-id="2ef09-117">The type of each element of `matrix`.</span></span>