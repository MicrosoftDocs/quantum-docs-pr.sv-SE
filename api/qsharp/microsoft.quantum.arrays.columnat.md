---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: Funktionen ColumnAt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210111"
---
# <a name="columnat-function"></a><span data-ttu-id="dfe15-102">Funktionen ColumnAt</span><span class="sxs-lookup"><span data-stu-id="dfe15-102">ColumnAt function</span></span>

<span data-ttu-id="dfe15-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dfe15-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dfe15-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dfe15-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dfe15-105">Extraherar en kolumn från en matris.</span><span class="sxs-lookup"><span data-stu-id="dfe15-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="dfe15-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="dfe15-106">Description</span></span>

<span data-ttu-id="dfe15-107">Den här funktionen extraherar en kolumn i en matris i rad-till-ordning.</span><span class="sxs-lookup"><span data-stu-id="dfe15-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="dfe15-108">Extrahera en rad corrsponds till element åtkomst för det första indexet och kräver därför ingen ytterligare behandling.</span><span class="sxs-lookup"><span data-stu-id="dfe15-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="dfe15-109">Indata</span><span class="sxs-lookup"><span data-stu-id="dfe15-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="dfe15-110">kolumn: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dfe15-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dfe15-111">Kolumn i matrisen</span><span class="sxs-lookup"><span data-stu-id="dfe15-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="dfe15-112">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="dfe15-112">matrix : 'T[][]</span></span>

<span data-ttu-id="dfe15-113">tvådimensionell matris i rad-till-ordning</span><span class="sxs-lookup"><span data-stu-id="dfe15-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="dfe15-114">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="dfe15-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dfe15-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="dfe15-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dfe15-116">Inte</span><span class="sxs-lookup"><span data-stu-id="dfe15-116">'T</span></span>

<span data-ttu-id="dfe15-117">Typen för varje element i `matrix` .</span><span class="sxs-lookup"><span data-stu-id="dfe15-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="dfe15-118">Se även</span><span class="sxs-lookup"><span data-stu-id="dfe15-118">See Also</span></span>

- [<span data-ttu-id="dfe15-119">Microsoft. Quantum. arrayer. transponeras</span><span class="sxs-lookup"><span data-stu-id="dfe15-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="dfe15-120">Microsoft. Quantum. Arrays. Diagonal</span><span class="sxs-lookup"><span data-stu-id="dfe15-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)