---
uid: Microsoft.Quantum.Arrays.Head
title: Huvud funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848579"
---
# <a name="head-function"></a><span data-ttu-id="f0c67-102">Huvud funktion</span><span class="sxs-lookup"><span data-stu-id="f0c67-102">Head function</span></span>

<span data-ttu-id="f0c67-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f0c67-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f0c67-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0c67-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0c67-105">Returnerar det första elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="f0c67-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="f0c67-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f0c67-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="f0c67-107">matris: "A []</span><span class="sxs-lookup"><span data-stu-id="f0c67-107">array : 'A[]</span></span>

<span data-ttu-id="f0c67-108">Matris som det första elementet ska hämtas från.</span><span class="sxs-lookup"><span data-stu-id="f0c67-108">Array of which the first element is taken.</span></span> <span data-ttu-id="f0c67-109">Matrisen måste ha en längd på minst 1.</span><span class="sxs-lookup"><span data-stu-id="f0c67-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="f0c67-110">Utdata: "A</span><span class="sxs-lookup"><span data-stu-id="f0c67-110">Output : 'A</span></span>

<span data-ttu-id="f0c67-111">Det första elementet i matrisen.</span><span class="sxs-lookup"><span data-stu-id="f0c67-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f0c67-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f0c67-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="f0c67-113">"A</span><span class="sxs-lookup"><span data-stu-id="f0c67-113">'A</span></span>

<span data-ttu-id="f0c67-114">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="f0c67-114">The type of the array elements.</span></span>