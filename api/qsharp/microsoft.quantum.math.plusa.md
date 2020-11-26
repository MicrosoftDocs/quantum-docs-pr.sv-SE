---
uid: Microsoft.Quantum.Math.PlusA
title: Plus-funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194839"
---
# <a name="plusa-function"></a><span data-ttu-id="df587-102">Plus-funktion</span><span class="sxs-lookup"><span data-stu-id="df587-102">PlusA function</span></span>

<span data-ttu-id="df587-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="df587-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="df587-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df587-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df587-105">Returnerar summan (sammanfogningen) av två indata.</span><span class="sxs-lookup"><span data-stu-id="df587-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="df587-106">Indata</span><span class="sxs-lookup"><span data-stu-id="df587-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="df587-107">a: ' element []</span><span class="sxs-lookup"><span data-stu-id="df587-107">a : 'Element[]</span></span>

<span data-ttu-id="df587-108">Den första indatamängden $a $ som ska summeras.</span><span class="sxs-lookup"><span data-stu-id="df587-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="df587-109">b: ' element []</span><span class="sxs-lookup"><span data-stu-id="df587-109">b : 'Element[]</span></span>

<span data-ttu-id="df587-110">Den andra indatamängden $b $ som ska summeras.</span><span class="sxs-lookup"><span data-stu-id="df587-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="df587-111">Output: ' element []</span><span class="sxs-lookup"><span data-stu-id="df587-111">Output : 'Element[]</span></span>

<span data-ttu-id="df587-112">Summan $a + b $.</span><span class="sxs-lookup"><span data-stu-id="df587-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="df587-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="df587-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="df587-114">' Element</span><span class="sxs-lookup"><span data-stu-id="df587-114">'Element</span></span>

<span data-ttu-id="df587-115">Typ av varje element i var och en av de två angivna matriserna.</span><span class="sxs-lookup"><span data-stu-id="df587-115">The type of each element in each of the two input arrays.</span></span>