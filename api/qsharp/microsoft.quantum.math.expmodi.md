---
uid: Microsoft.Quantum.Math.ExpModI
title: Funktionen ExpModI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732854"
---
# <a name="expmodi-function"></a><span data-ttu-id="e31ac-102">Funktionen ExpModI</span><span class="sxs-lookup"><span data-stu-id="e31ac-102">ExpModI function</span></span>

<span data-ttu-id="e31ac-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e31ac-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e31ac-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e31ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e31ac-105">Returnerar ett heltal som höjs till en specifik potens, med avseende på en specifik Modulus.</span><span class="sxs-lookup"><span data-stu-id="e31ac-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="e31ac-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e31ac-106">Description</span></span>

<span data-ttu-id="e31ac-107">Låt oss ange expBase i $x $, kraften $p $ och Modulus med $N $.</span><span class="sxs-lookup"><span data-stu-id="e31ac-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="e31ac-108">Funktionen returnerar $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="e31ac-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="e31ac-109">Vi förutsätter att $N $, $x $ är positiva och är inte negativt.</span><span class="sxs-lookup"><span data-stu-id="e31ac-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="e31ac-110">Indata</span><span class="sxs-lookup"><span data-stu-id="e31ac-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="e31ac-111">expBase: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e31ac-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="e31ac-112">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e31ac-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="e31ac-113">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e31ac-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="e31ac-114">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e31ac-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="e31ac-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="e31ac-115">Remarks</span></span>

<span data-ttu-id="e31ac-116">Tar tid i proportion till antalet bitar i `power` , inte `power` själva.</span><span class="sxs-lookup"><span data-stu-id="e31ac-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>