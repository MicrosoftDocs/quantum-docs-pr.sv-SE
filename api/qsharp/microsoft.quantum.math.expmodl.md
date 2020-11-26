---
uid: Microsoft.Quantum.Math.ExpModL
title: Funktionen ExpModL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210761"
---
# <a name="expmodl-function"></a><span data-ttu-id="b004e-102">Funktionen ExpModL</span><span class="sxs-lookup"><span data-stu-id="b004e-102">ExpModL function</span></span>

<span data-ttu-id="b004e-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b004e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b004e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b004e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b004e-105">Returnerar ett heltal som höjs till en specifik potens, med avseende på en specifik Modulus.</span><span class="sxs-lookup"><span data-stu-id="b004e-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="b004e-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b004e-106">Description</span></span>

<span data-ttu-id="b004e-107">Låt oss ange expBase i $x $, kraften $p $ och Modulus med $N $.</span><span class="sxs-lookup"><span data-stu-id="b004e-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="b004e-108">Funktionen returnerar $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="b004e-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="b004e-109">Vi förutsätter att $N $, $x $ är positiva och är inte negativt.</span><span class="sxs-lookup"><span data-stu-id="b004e-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="b004e-110">Indata</span><span class="sxs-lookup"><span data-stu-id="b004e-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="b004e-111">expBase: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b004e-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="b004e-112">effekt: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b004e-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="b004e-113">Modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b004e-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="b004e-114">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b004e-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="b004e-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b004e-115">Remarks</span></span>

<span data-ttu-id="b004e-116">Tar tid i proportion till antalet bitar i `power` , inte `power` själva.</span><span class="sxs-lookup"><span data-stu-id="b004e-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>