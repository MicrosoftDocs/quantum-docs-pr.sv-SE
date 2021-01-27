---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: Funktionen GreatestCommonDivisorL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 0f545f7888f5a9a353cc6000a12988648ac82dd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856381"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="e083c-102">Funktionen GreatestCommonDivisorL</span><span class="sxs-lookup"><span data-stu-id="e083c-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="e083c-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e083c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e083c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e083c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e083c-105">Beräknar den största gemensamma nämnaren i $a $ och $b $.</span><span class="sxs-lookup"><span data-stu-id="e083c-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="e083c-106">GCD är alltid positivt.</span><span class="sxs-lookup"><span data-stu-id="e083c-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="e083c-107">Indata</span><span class="sxs-lookup"><span data-stu-id="e083c-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="e083c-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e083c-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e083c-109">det första antalet som utökade största gemensamma divisor beräknas</span><span class="sxs-lookup"><span data-stu-id="e083c-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="e083c-110">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e083c-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e083c-111">det andra antalet som utökade största gemensamma divisor beräknas</span><span class="sxs-lookup"><span data-stu-id="e083c-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="e083c-112">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e083c-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e083c-113">Största gemensamma divisor i $a $ och $b $</span><span class="sxs-lookup"><span data-stu-id="e083c-113">Greatest common divisor of $a$ and $b$</span></span>