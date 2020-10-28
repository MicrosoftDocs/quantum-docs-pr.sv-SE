---
uid: Microsoft.Quantum.Arrays.Head
title: Huvud funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 7b26a9c414ab2caad70f96f3c26c2d1cf0b03e95
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730227"
---
# <a name="head-function"></a><span data-ttu-id="1697c-102">Huvud funktion</span><span class="sxs-lookup"><span data-stu-id="1697c-102">Head function</span></span>

<span data-ttu-id="1697c-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1697c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1697c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1697c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1697c-105">Returnerar det första elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="1697c-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="1697c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1697c-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="1697c-107">matris: "A []</span><span class="sxs-lookup"><span data-stu-id="1697c-107">array : 'A[]</span></span>

<span data-ttu-id="1697c-108">Matris som det första elementet ska hämtas från.</span><span class="sxs-lookup"><span data-stu-id="1697c-108">Array of which the first element is taken.</span></span> <span data-ttu-id="1697c-109">Matrisen måste ha en längd på minst 1.</span><span class="sxs-lookup"><span data-stu-id="1697c-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="1697c-110">Utdata: "A</span><span class="sxs-lookup"><span data-stu-id="1697c-110">Output : 'A</span></span>

<span data-ttu-id="1697c-111">Det första elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="1697c-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1697c-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="1697c-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="1697c-113">"A</span><span class="sxs-lookup"><span data-stu-id="1697c-113">'A</span></span>

<span data-ttu-id="1697c-114">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="1697c-114">The type of the array elements.</span></span>