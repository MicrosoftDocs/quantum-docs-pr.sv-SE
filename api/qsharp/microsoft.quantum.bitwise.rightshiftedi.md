---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: Funktionen RightShiftedI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845260"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="10fd7-102">Funktionen RightShiftedI</span><span class="sxs-lookup"><span data-stu-id="10fd7-102">RightShiftedI function</span></span>

<span data-ttu-id="10fd7-103">Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="10fd7-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="10fd7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="10fd7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="10fd7-105">Skiftar den bitvisa representationen av ett tal direkt med ett angivet antal bitar.</span><span class="sxs-lookup"><span data-stu-id="10fd7-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="10fd7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="10fd7-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="10fd7-107">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="10fd7-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="10fd7-108">Det tal vars bitvisa representation ska flyttas till höger (mindre signifikant).</span><span class="sxs-lookup"><span data-stu-id="10fd7-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="10fd7-109">belopp: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="10fd7-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="10fd7-110">Antalet bitar som ska `value` flyttas till höger.</span><span class="sxs-lookup"><span data-stu-id="10fd7-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="10fd7-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="10fd7-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="10fd7-112">Värdet för `value` , flyttas direkt med `amount` bitar.</span><span class="sxs-lookup"><span data-stu-id="10fd7-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="10fd7-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="10fd7-113">Remarks</span></span>

<span data-ttu-id="10fd7-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="10fd7-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```