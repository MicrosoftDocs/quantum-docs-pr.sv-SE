---
uid: Microsoft.Quantum.Math.ExpModI
title: Funktionen ExpModI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 197f7351ce76ebb7684ca8014cab9ab65d9c784c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228499"
---
# <a name="expmodi-function"></a><span data-ttu-id="6f44d-102">Funktionen ExpModI</span><span class="sxs-lookup"><span data-stu-id="6f44d-102">ExpModI function</span></span>

<span data-ttu-id="6f44d-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6f44d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6f44d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f44d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f44d-105">Returnerar ett heltal som höjs till en specifik potens, med avseende på en specifik Modulus.</span><span class="sxs-lookup"><span data-stu-id="6f44d-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="6f44d-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6f44d-106">Description</span></span>

<span data-ttu-id="6f44d-107">Låt oss ange expBase i $x $, kraften $p $ och Modulus med $N $.</span><span class="sxs-lookup"><span data-stu-id="6f44d-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="6f44d-108">Funktionen returnerar $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="6f44d-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="6f44d-109">Vi förutsätter att $N $, $x $ är positiva och är inte negativt.</span><span class="sxs-lookup"><span data-stu-id="6f44d-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="6f44d-110">Indata</span><span class="sxs-lookup"><span data-stu-id="6f44d-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="6f44d-111">expBase: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f44d-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="6f44d-112">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f44d-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="6f44d-113">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f44d-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="6f44d-114">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f44d-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="6f44d-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6f44d-115">Remarks</span></span>

<span data-ttu-id="6f44d-116">Tar tid i proportion till antalet bitar i `power` , inte `power` själva.</span><span class="sxs-lookup"><span data-stu-id="6f44d-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>