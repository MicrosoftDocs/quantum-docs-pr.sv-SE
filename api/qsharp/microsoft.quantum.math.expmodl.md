---
uid: Microsoft.Quantum.Math.ExpModL
title: Funktionen ExpModL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 127f2e51e19c76f4f7973bf1ac2217d4fffd72f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848359"
---
# <a name="expmodl-function"></a><span data-ttu-id="02aa5-102">Funktionen ExpModL</span><span class="sxs-lookup"><span data-stu-id="02aa5-102">ExpModL function</span></span>

<span data-ttu-id="02aa5-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="02aa5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="02aa5-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02aa5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02aa5-105">Returnerar ett heltal som höjs till en specifik potens, med avseende på en specifik Modulus.</span><span class="sxs-lookup"><span data-stu-id="02aa5-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="02aa5-106">Description</span><span class="sxs-lookup"><span data-stu-id="02aa5-106">Description</span></span>

<span data-ttu-id="02aa5-107">Låt oss ange expBase i $x $, kraften $p $ och Modulus med $N $.</span><span class="sxs-lookup"><span data-stu-id="02aa5-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="02aa5-108">Funktionen returnerar $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="02aa5-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="02aa5-109">Vi förutsätter att $N $, $x $ är positiva och är inte negativt.</span><span class="sxs-lookup"><span data-stu-id="02aa5-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="02aa5-110">Indata</span><span class="sxs-lookup"><span data-stu-id="02aa5-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="02aa5-111">expBase: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="02aa5-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="02aa5-112">effekt: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="02aa5-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="02aa5-113">Modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="02aa5-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="02aa5-114">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="02aa5-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="02aa5-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="02aa5-115">Remarks</span></span>

<span data-ttu-id="02aa5-116">Tar tid i proportion till antalet bitar i `power` , inte `power` själva.</span><span class="sxs-lookup"><span data-stu-id="02aa5-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>