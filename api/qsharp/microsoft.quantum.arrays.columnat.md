---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: Funktionen ColumnAt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730406"
---
# <a name="columnat-function"></a><span data-ttu-id="b95bd-102">Funktionen ColumnAt</span><span class="sxs-lookup"><span data-stu-id="b95bd-102">ColumnAt function</span></span>

<span data-ttu-id="b95bd-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b95bd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b95bd-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b95bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b95bd-105">Extraherar en kolumn från en matris.</span><span class="sxs-lookup"><span data-stu-id="b95bd-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="b95bd-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b95bd-106">Description</span></span>

<span data-ttu-id="b95bd-107">Den här funktionen extraherar en kolumn i en matris i rad-till-ordning.</span><span class="sxs-lookup"><span data-stu-id="b95bd-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="b95bd-108">Extrahera en rad corrsponds till element åtkomst för det första indexet och kräver därför ingen ytterligare behandling.</span><span class="sxs-lookup"><span data-stu-id="b95bd-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="b95bd-109">Indata</span><span class="sxs-lookup"><span data-stu-id="b95bd-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="b95bd-110">kolumn: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b95bd-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b95bd-111">Kolumn i matrisen</span><span class="sxs-lookup"><span data-stu-id="b95bd-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="b95bd-112">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="b95bd-112">matrix : 'T[][]</span></span>

<span data-ttu-id="b95bd-113">tvådimensionell matris i rad-till-ordning</span><span class="sxs-lookup"><span data-stu-id="b95bd-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="b95bd-114">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="b95bd-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b95bd-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="b95bd-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b95bd-116">Inte</span><span class="sxs-lookup"><span data-stu-id="b95bd-116">'T</span></span>

<span data-ttu-id="b95bd-117">Typen för varje element i `matrix` .</span><span class="sxs-lookup"><span data-stu-id="b95bd-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b95bd-118">Se även</span><span class="sxs-lookup"><span data-stu-id="b95bd-118">See Also</span></span>

- [<span data-ttu-id="b95bd-119">Microsoft. Quantum. arrayer. transponeras</span><span class="sxs-lookup"><span data-stu-id="b95bd-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="b95bd-120">Microsoft. Quantum. Arrays. Diagonal</span><span class="sxs-lookup"><span data-stu-id="b95bd-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)