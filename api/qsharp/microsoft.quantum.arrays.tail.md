---
uid: Microsoft.Quantum.Arrays.Tail
title: Funktionen pilslut
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729982"
---
# <a name="tail-function"></a><span data-ttu-id="1e551-102">Funktionen pilslut</span><span class="sxs-lookup"><span data-stu-id="1e551-102">Tail function</span></span>

<span data-ttu-id="1e551-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1e551-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1e551-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e551-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e551-105">Returnerar det sista elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="1e551-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="1e551-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1e551-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="1e551-107">matris: "A []</span><span class="sxs-lookup"><span data-stu-id="1e551-107">array : 'A[]</span></span>

<span data-ttu-id="1e551-108">Matris som det sista elementet tar med.</span><span class="sxs-lookup"><span data-stu-id="1e551-108">Array of which the last element is taken.</span></span> <span data-ttu-id="1e551-109">Matrisen måste ha en längd på minst 1.</span><span class="sxs-lookup"><span data-stu-id="1e551-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="1e551-110">Utdata: "A</span><span class="sxs-lookup"><span data-stu-id="1e551-110">Output : 'A</span></span>

<span data-ttu-id="1e551-111">Det sista elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="1e551-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1e551-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="1e551-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="1e551-113">"A</span><span class="sxs-lookup"><span data-stu-id="1e551-113">'A</span></span>

<span data-ttu-id="1e551-114">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="1e551-114">The type of the array elements.</span></span>