---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Diagonal funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221546"
---
# <a name="diagonal-function"></a><span data-ttu-id="8789e-102">Diagonal funktion</span><span class="sxs-lookup"><span data-stu-id="8789e-102">Diagonal function</span></span>

<span data-ttu-id="8789e-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8789e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8789e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8789e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8789e-105">Returnerar en matris med diagonala element i en tvådimensionell matris</span><span class="sxs-lookup"><span data-stu-id="8789e-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="8789e-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8789e-106">Description</span></span>

<span data-ttu-id="8789e-107">Om den tvådimensionella matrisen inte har någon kvadratisk form returneras diagonalen över minimivärdet över antalet rader och kolumner.</span><span class="sxs-lookup"><span data-stu-id="8789e-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="8789e-108">Indata</span><span class="sxs-lookup"><span data-stu-id="8789e-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="8789e-109">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="8789e-109">matrix : 'T[][]</span></span>

<span data-ttu-id="8789e-110">tvådimensionell matris i rad-till-ordning</span><span class="sxs-lookup"><span data-stu-id="8789e-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="8789e-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="8789e-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8789e-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8789e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8789e-113">Inte</span><span class="sxs-lookup"><span data-stu-id="8789e-113">'T</span></span>

<span data-ttu-id="8789e-114">Typen för varje element i `matrix` .</span><span class="sxs-lookup"><span data-stu-id="8789e-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8789e-115">Se även</span><span class="sxs-lookup"><span data-stu-id="8789e-115">See Also</span></span>

- [<span data-ttu-id="8789e-116">Microsoft. Quantum. arrayer. transponeras</span><span class="sxs-lookup"><span data-stu-id="8789e-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)