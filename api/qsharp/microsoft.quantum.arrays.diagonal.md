---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Diagonal funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842829"
---
# <a name="diagonal-function"></a><span data-ttu-id="13c97-102">Diagonal funktion</span><span class="sxs-lookup"><span data-stu-id="13c97-102">Diagonal function</span></span>

<span data-ttu-id="13c97-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="13c97-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="13c97-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13c97-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13c97-105">Returnerar en matris med diagonala element i en tvådimensionell matris</span><span class="sxs-lookup"><span data-stu-id="13c97-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="13c97-106">Description</span><span class="sxs-lookup"><span data-stu-id="13c97-106">Description</span></span>

<span data-ttu-id="13c97-107">Om den tvådimensionella matrisen inte har någon kvadratisk form returneras diagonalen över minimivärdet över antalet rader och kolumner.</span><span class="sxs-lookup"><span data-stu-id="13c97-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="13c97-108">Indata</span><span class="sxs-lookup"><span data-stu-id="13c97-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="13c97-109">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="13c97-109">matrix : 'T[][]</span></span>

<span data-ttu-id="13c97-110">tvådimensionell matris i rad-till-ordning</span><span class="sxs-lookup"><span data-stu-id="13c97-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="13c97-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="13c97-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="13c97-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="13c97-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="13c97-113">Inte</span><span class="sxs-lookup"><span data-stu-id="13c97-113">'T</span></span>

<span data-ttu-id="13c97-114">Typen för varje element i `matrix` .</span><span class="sxs-lookup"><span data-stu-id="13c97-114">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="13c97-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="13c97-115">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a><span data-ttu-id="13c97-116">Se även</span><span class="sxs-lookup"><span data-stu-id="13c97-116">See Also</span></span>

- [<span data-ttu-id="13c97-117">Microsoft. Quantum. arrayer. transponeras</span><span class="sxs-lookup"><span data-stu-id="13c97-117">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)