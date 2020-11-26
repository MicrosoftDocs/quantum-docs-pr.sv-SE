---
uid: Microsoft.Quantum.Arrays.Head
title: Huvud funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221121"
---
# <a name="head-function"></a><span data-ttu-id="74363-102">Huvud funktion</span><span class="sxs-lookup"><span data-stu-id="74363-102">Head function</span></span>

<span data-ttu-id="74363-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="74363-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="74363-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="74363-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="74363-105">Returnerar det första elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="74363-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="74363-106">Indata</span><span class="sxs-lookup"><span data-stu-id="74363-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="74363-107">matris: "A []</span><span class="sxs-lookup"><span data-stu-id="74363-107">array : 'A[]</span></span>

<span data-ttu-id="74363-108">Matris som det första elementet ska hämtas från.</span><span class="sxs-lookup"><span data-stu-id="74363-108">Array of which the first element is taken.</span></span> <span data-ttu-id="74363-109">Matrisen måste ha en längd på minst 1.</span><span class="sxs-lookup"><span data-stu-id="74363-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="74363-110">Utdata: "A</span><span class="sxs-lookup"><span data-stu-id="74363-110">Output : 'A</span></span>

<span data-ttu-id="74363-111">Det första elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="74363-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="74363-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="74363-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="74363-113">"A</span><span class="sxs-lookup"><span data-stu-id="74363-113">'A</span></span>

<span data-ttu-id="74363-114">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="74363-114">The type of the array elements.</span></span>