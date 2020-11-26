---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: Funktionen GreatestCommonDivisorL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 1bd18758bb2dea8a4801cbfdf258d91f81c5d9a4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195519"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="f4295-102">Funktionen GreatestCommonDivisorL</span><span class="sxs-lookup"><span data-stu-id="f4295-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="f4295-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f4295-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f4295-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4295-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4295-105">Beräknar den största gemensamma nämnaren i $a $ och $b $.</span><span class="sxs-lookup"><span data-stu-id="f4295-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="f4295-106">GCD är alltid positivt.</span><span class="sxs-lookup"><span data-stu-id="f4295-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="f4295-107">Indata</span><span class="sxs-lookup"><span data-stu-id="f4295-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="f4295-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f4295-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f4295-109">det första antalet som utökade största gemensamma divisor beräknas</span><span class="sxs-lookup"><span data-stu-id="f4295-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="f4295-110">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f4295-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f4295-111">det andra antalet som utökade största gemensamma divisor beräknas</span><span class="sxs-lookup"><span data-stu-id="f4295-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="f4295-112">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f4295-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f4295-113">Största gemensamma divisor i $a $ och $b $</span><span class="sxs-lookup"><span data-stu-id="f4295-113">Greatest common divisor of $a$ and $b$</span></span>