---
uid: Microsoft.Quantum.Arrays.Tail
title: Funktionen pilslut
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220101"
---
# <a name="tail-function"></a><span data-ttu-id="086a6-102">Funktionen pilslut</span><span class="sxs-lookup"><span data-stu-id="086a6-102">Tail function</span></span>

<span data-ttu-id="086a6-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="086a6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="086a6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="086a6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="086a6-105">Returnerar det sista elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="086a6-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="086a6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="086a6-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="086a6-107">matris: "A []</span><span class="sxs-lookup"><span data-stu-id="086a6-107">array : 'A[]</span></span>

<span data-ttu-id="086a6-108">Matris som det sista elementet tar med.</span><span class="sxs-lookup"><span data-stu-id="086a6-108">Array of which the last element is taken.</span></span> <span data-ttu-id="086a6-109">Matrisen måste ha en längd på minst 1.</span><span class="sxs-lookup"><span data-stu-id="086a6-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="086a6-110">Utdata: "A</span><span class="sxs-lookup"><span data-stu-id="086a6-110">Output : 'A</span></span>

<span data-ttu-id="086a6-111">Det sista elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="086a6-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="086a6-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="086a6-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="086a6-113">"A</span><span class="sxs-lookup"><span data-stu-id="086a6-113">'A</span></span>

<span data-ttu-id="086a6-114">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="086a6-114">The type of the array elements.</span></span>