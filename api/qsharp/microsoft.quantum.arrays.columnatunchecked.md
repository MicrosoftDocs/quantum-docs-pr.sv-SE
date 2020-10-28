---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: Funktionen ColumnAtUnchecked
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 17211c1ae1fe12fcadf34a9411f9b0cf0cdcab50
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730403"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="b2410-102">Funktionen ColumnAtUnchecked</span><span class="sxs-lookup"><span data-stu-id="b2410-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="b2410-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b2410-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b2410-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2410-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2410-105">Den här funktionen söker inte efter mat ris former</span><span class="sxs-lookup"><span data-stu-id="b2410-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="b2410-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b2410-106">Description</span></span>

<span data-ttu-id="b2410-107">Den här funktionen kan användas i andra flerdimensionella funktioner som redan kontrollerar Indataporten för en giltig rektangulär form.</span><span class="sxs-lookup"><span data-stu-id="b2410-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="b2410-108">Indata</span><span class="sxs-lookup"><span data-stu-id="b2410-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="b2410-109">kolumn: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b2410-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="b2410-110">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="b2410-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="b2410-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="b2410-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b2410-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="b2410-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b2410-113">Inte</span><span class="sxs-lookup"><span data-stu-id="b2410-113">'T</span></span>

