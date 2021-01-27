---
uid: Microsoft.Quantum.Math.ExpModI
title: Funktionen ExpModI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857038"
---
# <a name="expmodi-function"></a><span data-ttu-id="e53d2-102">Funktionen ExpModI</span><span class="sxs-lookup"><span data-stu-id="e53d2-102">ExpModI function</span></span>

<span data-ttu-id="e53d2-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e53d2-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e53d2-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e53d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e53d2-105">Returnerar ett heltal som höjs till en specifik potens, med avseende på en specifik Modulus.</span><span class="sxs-lookup"><span data-stu-id="e53d2-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="e53d2-106">Description</span><span class="sxs-lookup"><span data-stu-id="e53d2-106">Description</span></span>

<span data-ttu-id="e53d2-107">Låt oss ange expBase i $x $, kraften $p $ och Modulus med $N $.</span><span class="sxs-lookup"><span data-stu-id="e53d2-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="e53d2-108">Funktionen returnerar $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="e53d2-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="e53d2-109">Vi förutsätter att $N $, $x $ är positiva och är inte negativt.</span><span class="sxs-lookup"><span data-stu-id="e53d2-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="e53d2-110">Indata</span><span class="sxs-lookup"><span data-stu-id="e53d2-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="e53d2-111">expBase: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e53d2-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="e53d2-112">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e53d2-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="e53d2-113">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e53d2-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="e53d2-114">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e53d2-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="e53d2-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="e53d2-115">Remarks</span></span>

<span data-ttu-id="e53d2-116">Tar tid i proportion till antalet bitar i `power` , inte `power` själva.</span><span class="sxs-lookup"><span data-stu-id="e53d2-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>