---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: Funktionen ColumnAt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846262"
---
# <a name="columnat-function"></a><span data-ttu-id="d4e9c-102">Funktionen ColumnAt</span><span class="sxs-lookup"><span data-stu-id="d4e9c-102">ColumnAt function</span></span>

<span data-ttu-id="d4e9c-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d4e9c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d4e9c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4e9c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4e9c-105">Extraherar en kolumn från en matris.</span><span class="sxs-lookup"><span data-stu-id="d4e9c-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="d4e9c-106">Description</span><span class="sxs-lookup"><span data-stu-id="d4e9c-106">Description</span></span>

<span data-ttu-id="d4e9c-107">Den här funktionen extraherar en kolumn i en matris i rad-till-ordning.</span><span class="sxs-lookup"><span data-stu-id="d4e9c-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="d4e9c-108">Extrahera en rad corrsponds till element åtkomst för det första indexet och kräver därför ingen ytterligare behandling.</span><span class="sxs-lookup"><span data-stu-id="d4e9c-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="d4e9c-109">Indata</span><span class="sxs-lookup"><span data-stu-id="d4e9c-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="d4e9c-110">kolumn: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4e9c-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d4e9c-111">Kolumn i matrisen</span><span class="sxs-lookup"><span data-stu-id="d4e9c-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="d4e9c-112">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="d4e9c-112">matrix : 'T[][]</span></span>

<span data-ttu-id="d4e9c-113">tvådimensionell matris i rad-till-ordning</span><span class="sxs-lookup"><span data-stu-id="d4e9c-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="d4e9c-114">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="d4e9c-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d4e9c-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="d4e9c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d4e9c-116">Inte</span><span class="sxs-lookup"><span data-stu-id="d4e9c-116">'T</span></span>

<span data-ttu-id="d4e9c-117">Typen för varje element i `matrix` .</span><span class="sxs-lookup"><span data-stu-id="d4e9c-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="d4e9c-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="d4e9c-118">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a><span data-ttu-id="d4e9c-119">Se även</span><span class="sxs-lookup"><span data-stu-id="d4e9c-119">See Also</span></span>

- [<span data-ttu-id="d4e9c-120">Microsoft. Quantum. arrayer. transponeras</span><span class="sxs-lookup"><span data-stu-id="d4e9c-120">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="d4e9c-121">Microsoft. Quantum. Arrays. Diagonal</span><span class="sxs-lookup"><span data-stu-id="d4e9c-121">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)