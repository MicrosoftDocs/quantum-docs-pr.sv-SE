---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: Funktionen ExtendedGreatestCommonDivisorI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 365e91e84add0d57d5a3cf203bbf23d96979b251
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195535"
---
# <a name="extendedgreatestcommondivisori-function"></a><span data-ttu-id="3ebe1-102">Funktionen ExtendedGreatestCommonDivisorI</span><span class="sxs-lookup"><span data-stu-id="3ebe1-102">ExtendedGreatestCommonDivisorI function</span></span>

<span data-ttu-id="3ebe1-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3ebe1-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3ebe1-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ebe1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ebe1-105">Beräknar en tupel $ (u, v) $ så att $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, där $ \operatorname{GCD} $ är $a $ största gemensamma divisor av $a $ och $b $.</span><span class="sxs-lookup"><span data-stu-id="3ebe1-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="3ebe1-106">GCD är alltid positivt.</span><span class="sxs-lookup"><span data-stu-id="3ebe1-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a><span data-ttu-id="3ebe1-107">Indata</span><span class="sxs-lookup"><span data-stu-id="3ebe1-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="3ebe1-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ebe1-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ebe1-109">det första antalet som utökade största gemensamma divisor beräknas</span><span class="sxs-lookup"><span data-stu-id="3ebe1-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="3ebe1-110">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ebe1-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ebe1-111">det andra antalet som utökade största gemensamma divisor beräknas</span><span class="sxs-lookup"><span data-stu-id="3ebe1-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--intint"></a><span data-ttu-id="3ebe1-112">Utdata: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="3ebe1-112">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="3ebe1-113">Tupel $ (u, v) $ med egenskapen $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.</span><span class="sxs-lookup"><span data-stu-id="3ebe1-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="3ebe1-114">Referenser</span><span class="sxs-lookup"><span data-stu-id="3ebe1-114">References</span></span>

- <span data-ttu-id="3ebe1-115">Den här implementeringen sker enligt https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="3ebe1-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>