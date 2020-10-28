---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: Funktionen GreatestCommonDivisorL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 77bdb040908e9a8af81dee09451a3582f7b7d159
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733014"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="5e851-102">Funktionen GreatestCommonDivisorL</span><span class="sxs-lookup"><span data-stu-id="5e851-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="5e851-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5e851-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5e851-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e851-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e851-105">Beräknar den största gemensamma nämnaren i $a $ och $b $.</span><span class="sxs-lookup"><span data-stu-id="5e851-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="5e851-106">GCD är alltid positivt.</span><span class="sxs-lookup"><span data-stu-id="5e851-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="5e851-107">Indata</span><span class="sxs-lookup"><span data-stu-id="5e851-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="5e851-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5e851-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5e851-109">det första antalet som utökade största gemensamma divisor beräknas</span><span class="sxs-lookup"><span data-stu-id="5e851-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="5e851-110">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5e851-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5e851-111">det andra antalet som utökade största gemensamma divisor beräknas</span><span class="sxs-lookup"><span data-stu-id="5e851-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="5e851-112">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5e851-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5e851-113">Största gemensamma divisor i $a $ och $b $</span><span class="sxs-lookup"><span data-stu-id="5e851-113">Greatest common divisor of $a$ and $b$</span></span>