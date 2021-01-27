---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: Funktionen LeftShiftedI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845311"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="5c728-102">Funktionen LeftShiftedI</span><span class="sxs-lookup"><span data-stu-id="5c728-102">LeftShiftedI function</span></span>

<span data-ttu-id="5c728-103">Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="5c728-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="5c728-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c728-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5c728-105">Växlar den bitvisa representationen av ett tal till vänster med ett angivet antal bitar.</span><span class="sxs-lookup"><span data-stu-id="5c728-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="5c728-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5c728-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="5c728-107">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c728-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5c728-108">Det tal vars bitvisa representation ska flyttas till vänster (mer signifikant).</span><span class="sxs-lookup"><span data-stu-id="5c728-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="5c728-109">belopp: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c728-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5c728-110">Antalet bitar som ska `value` flyttas till vänster.</span><span class="sxs-lookup"><span data-stu-id="5c728-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="5c728-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c728-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5c728-112">Värdet för `value` , flyttas till vänster med `amount` bitar.</span><span class="sxs-lookup"><span data-stu-id="5c728-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c728-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5c728-113">Remarks</span></span>

<span data-ttu-id="5c728-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="5c728-114">The following are equivalent:</span></span>

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```