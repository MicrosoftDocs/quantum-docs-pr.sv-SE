---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: Funktionen ColumnAtUnchecked
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 06fce23bbf7142ee0e0b0ed3f2c0578676f2097b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221597"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="57d9a-102">Funktionen ColumnAtUnchecked</span><span class="sxs-lookup"><span data-stu-id="57d9a-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="57d9a-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="57d9a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="57d9a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57d9a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57d9a-105">Den här funktionen söker inte efter mat ris former</span><span class="sxs-lookup"><span data-stu-id="57d9a-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="57d9a-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="57d9a-106">Description</span></span>

<span data-ttu-id="57d9a-107">Den här funktionen kan användas i andra flerdimensionella funktioner som redan kontrollerar Indataporten för en giltig rektangulär form.</span><span class="sxs-lookup"><span data-stu-id="57d9a-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="57d9a-108">Indata</span><span class="sxs-lookup"><span data-stu-id="57d9a-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="57d9a-109">kolumn: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57d9a-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="57d9a-110">matris: ' ' [] []</span><span class="sxs-lookup"><span data-stu-id="57d9a-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="57d9a-111">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="57d9a-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="57d9a-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="57d9a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="57d9a-113">Inte</span><span class="sxs-lookup"><span data-stu-id="57d9a-113">'T</span></span>

