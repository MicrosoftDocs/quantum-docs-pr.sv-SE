---
uid: Microsoft.Quantum.Arrays.Tail
title: Funktionen pilslut
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 680562228a39263ef87ba053e6b7683412947e46
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845413"
---
# <a name="tail-function"></a><span data-ttu-id="8ccd5-102">Funktionen pilslut</span><span class="sxs-lookup"><span data-stu-id="8ccd5-102">Tail function</span></span>

<span data-ttu-id="8ccd5-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8ccd5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8ccd5-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ccd5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ccd5-105">Returnerar det sista elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="8ccd5-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="8ccd5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8ccd5-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="8ccd5-107">matris: "A []</span><span class="sxs-lookup"><span data-stu-id="8ccd5-107">array : 'A[]</span></span>

<span data-ttu-id="8ccd5-108">Matris som det sista elementet tar med.</span><span class="sxs-lookup"><span data-stu-id="8ccd5-108">Array of which the last element is taken.</span></span> <span data-ttu-id="8ccd5-109">Matrisen måste ha en längd på minst 1.</span><span class="sxs-lookup"><span data-stu-id="8ccd5-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="8ccd5-110">Utdata: "A</span><span class="sxs-lookup"><span data-stu-id="8ccd5-110">Output : 'A</span></span>

<span data-ttu-id="8ccd5-111">Det sista elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="8ccd5-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8ccd5-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8ccd5-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="8ccd5-113">"A</span><span class="sxs-lookup"><span data-stu-id="8ccd5-113">'A</span></span>

<span data-ttu-id="8ccd5-114">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="8ccd5-114">The type of the array elements.</span></span>