---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: Funktionen LeftShiftedL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729859"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="07988-102">Funktionen LeftShiftedL</span><span class="sxs-lookup"><span data-stu-id="07988-102">LeftShiftedL function</span></span>

<span data-ttu-id="07988-103">Namnrymd: [Microsoft. Quantum. bitvis](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="07988-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="07988-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07988-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07988-105">Växlar den bitvisa representationen av ett tal till vänster med ett angivet antal bitar.</span><span class="sxs-lookup"><span data-stu-id="07988-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="07988-106">Indata</span><span class="sxs-lookup"><span data-stu-id="07988-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="07988-107">värde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="07988-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="07988-108">Det tal vars bitvisa representation ska flyttas till vänster (mer signifikant).</span><span class="sxs-lookup"><span data-stu-id="07988-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="07988-109">belopp: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="07988-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="07988-110">Antalet bitar som ska `value` flyttas till vänster.</span><span class="sxs-lookup"><span data-stu-id="07988-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="07988-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="07988-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="07988-112">Värdet för `value` , flyttas till vänster med `amount` bitar.</span><span class="sxs-lookup"><span data-stu-id="07988-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="07988-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="07988-113">Remarks</span></span>

<span data-ttu-id="07988-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="07988-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```