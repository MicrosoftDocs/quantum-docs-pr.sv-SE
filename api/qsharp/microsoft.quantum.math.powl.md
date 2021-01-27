---
uid: Microsoft.Quantum.Math.PowL
title: Funktionen PowL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: f7282a3639ca87dae731e39594576aa73c4602ac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857455"
---
# <a name="powl-function"></a><span data-ttu-id="ad012-102">Funktionen PowL</span><span class="sxs-lookup"><span data-stu-id="ad012-102">PowL function</span></span>

<span data-ttu-id="ad012-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ad012-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ad012-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad012-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad012-105">Returnerar ett tal upphöjt till en specifik potens.</span><span class="sxs-lookup"><span data-stu-id="ad012-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="ad012-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ad012-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="ad012-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ad012-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ad012-108">Talet $a $ som ska höjas.</span><span class="sxs-lookup"><span data-stu-id="ad012-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="ad012-109">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ad012-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ad012-110">Power $b $ som $a $ ska höjas till.</span><span class="sxs-lookup"><span data-stu-id="ad012-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="ad012-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ad012-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ad012-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="ad012-112">The power $a^b$</span></span>