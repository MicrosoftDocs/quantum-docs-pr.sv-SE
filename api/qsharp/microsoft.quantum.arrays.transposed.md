---
uid: Microsoft.Quantum.Arrays.Transposed
title: Transponerad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850940"
---
# <a name="transposed-function"></a><span data-ttu-id="d2046-102">Transponerad funktion</span><span class="sxs-lookup"><span data-stu-id="d2046-102">Transposed function</span></span>

<span data-ttu-id="d2046-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d2046-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d2046-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2046-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2046-105">Returnerar Transponeringen av en matris som visas som en matris med matriser.</span><span class="sxs-lookup"><span data-stu-id="d2046-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="d2046-106">Description</span><span class="sxs-lookup"><span data-stu-id="d2046-106">Description</span></span>

<span data-ttu-id="d2046-107">Mata in som en $r \times c $-matris med $r $ rader och $c $ columns.</span><span class="sxs-lookup"><span data-stu-id="d2046-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="d2046-108">Matrisen är rad-baserad, d.v.s. kommer att `matrix[i][j]` få åtkomst till elementet på rad $i $ och kolumn $j $.</span><span class="sxs-lookup"><span data-stu-id="d2046-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="d2046-109">Den här funktionen returnerar den $c \times r $-matrisen som är transponerad för den angivna matrisen.</span><span class="sxs-lookup"><span data-stu-id="d2046-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="d2046-110">Indata</span><span class="sxs-lookup"><span data-stu-id="d2046-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="d2046-111">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="d2046-111">matrix : 'T[][]</span></span>

<span data-ttu-id="d2046-112">Rad-baserad $r \times c $ Matrix</span><span class="sxs-lookup"><span data-stu-id="d2046-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="d2046-113">Utdata: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="d2046-113">Output : 'T[][]</span></span>

<span data-ttu-id="d2046-114">Transponerad $c \times r $ Matrix</span><span class="sxs-lookup"><span data-stu-id="d2046-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d2046-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="d2046-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d2046-116">Inte</span><span class="sxs-lookup"><span data-stu-id="d2046-116">'T</span></span>

<span data-ttu-id="d2046-117">Typen för varje element i `matrix` .</span><span class="sxs-lookup"><span data-stu-id="d2046-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="d2046-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="d2046-118">Example</span></span>

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```