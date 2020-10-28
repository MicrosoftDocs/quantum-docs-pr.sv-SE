---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Diagonal funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730358"
---
# <a name="diagonal-function"></a><span data-ttu-id="96d1a-102">Diagonal funktion</span><span class="sxs-lookup"><span data-stu-id="96d1a-102">Diagonal function</span></span>

<span data-ttu-id="96d1a-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="96d1a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="96d1a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96d1a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96d1a-105">Returnerar en matris med diagonala element i en tvådimensionell matris</span><span class="sxs-lookup"><span data-stu-id="96d1a-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="96d1a-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="96d1a-106">Description</span></span>

<span data-ttu-id="96d1a-107">Om den tvådimensionella matrisen inte har någon kvadratisk form returneras diagonalen över minimivärdet över antalet rader och kolumner.</span><span class="sxs-lookup"><span data-stu-id="96d1a-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="96d1a-108">Indata</span><span class="sxs-lookup"><span data-stu-id="96d1a-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="96d1a-109">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="96d1a-109">matrix : 'T[][]</span></span>

<span data-ttu-id="96d1a-110">tvådimensionell matris i rad-till-ordning</span><span class="sxs-lookup"><span data-stu-id="96d1a-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="96d1a-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="96d1a-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="96d1a-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="96d1a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="96d1a-113">Inte</span><span class="sxs-lookup"><span data-stu-id="96d1a-113">'T</span></span>

<span data-ttu-id="96d1a-114">Typen för varje element i `matrix` .</span><span class="sxs-lookup"><span data-stu-id="96d1a-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="96d1a-115">Se även</span><span class="sxs-lookup"><span data-stu-id="96d1a-115">See Also</span></span>

- [<span data-ttu-id="96d1a-116">Microsoft. Quantum. arrayer. transponeras</span><span class="sxs-lookup"><span data-stu-id="96d1a-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)