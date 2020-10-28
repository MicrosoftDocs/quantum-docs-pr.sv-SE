---
uid: Microsoft.Quantum.Math.PlusA
title: Plus-funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725887"
---
# <a name="plusa-function"></a><span data-ttu-id="60d08-102">Plus-funktion</span><span class="sxs-lookup"><span data-stu-id="60d08-102">PlusA function</span></span>

<span data-ttu-id="60d08-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="60d08-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="60d08-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="60d08-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="60d08-105">Returnerar summan (sammanfogningen) av två indata.</span><span class="sxs-lookup"><span data-stu-id="60d08-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="60d08-106">Indata</span><span class="sxs-lookup"><span data-stu-id="60d08-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="60d08-107">a: ' element []</span><span class="sxs-lookup"><span data-stu-id="60d08-107">a : 'Element[]</span></span>

<span data-ttu-id="60d08-108">Den första indatamängden $a $ som ska summeras.</span><span class="sxs-lookup"><span data-stu-id="60d08-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="60d08-109">b: ' element []</span><span class="sxs-lookup"><span data-stu-id="60d08-109">b : 'Element[]</span></span>

<span data-ttu-id="60d08-110">Den andra indatamängden $b $ som ska summeras.</span><span class="sxs-lookup"><span data-stu-id="60d08-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="60d08-111">Output: ' element []</span><span class="sxs-lookup"><span data-stu-id="60d08-111">Output : 'Element[]</span></span>

<span data-ttu-id="60d08-112">Summan $a + b $.</span><span class="sxs-lookup"><span data-stu-id="60d08-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="60d08-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="60d08-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="60d08-114">' Element</span><span class="sxs-lookup"><span data-stu-id="60d08-114">'Element</span></span>

<span data-ttu-id="60d08-115">Typ av varje element i var och en av de två angivna matriserna.</span><span class="sxs-lookup"><span data-stu-id="60d08-115">The type of each element in each of the two input arrays.</span></span>