---
uid: Microsoft.Quantum.Math.ModulusL
title: Modulus-funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: e7e692059051fde295634c37892ec54e2cf1b095
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733846"
---
# <a name="modulusl-function"></a><span data-ttu-id="cbacb-102">Modulus-funktion</span><span class="sxs-lookup"><span data-stu-id="cbacb-102">ModulusL function</span></span>

<span data-ttu-id="cbacb-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cbacb-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cbacb-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cbacb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cbacb-105">Beräknar de kanoniska resterna av `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="cbacb-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="cbacb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="cbacb-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="cbacb-107">värde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cbacb-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cbacb-108">Värdet för vilken restsubstanser beräknas</span><span class="sxs-lookup"><span data-stu-id="cbacb-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="cbacb-109">Modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cbacb-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cbacb-110">Den modul som rester tar emot måste vara positiva</span><span class="sxs-lookup"><span data-stu-id="cbacb-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="cbacb-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cbacb-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cbacb-112">Heltal $r $ mellan 0 och `modulus - 1` som `value - r` är delbar med modulus</span><span class="sxs-lookup"><span data-stu-id="cbacb-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="cbacb-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="cbacb-113">Remarks</span></span>

<span data-ttu-id="cbacb-114">Den här funktionen fungerar annorlunda för hur operatorn `%` beter sig i C# och Q # som i resultatet är alltid ett positivt heltal mellan 0 och `modulus - 1` , även om värdet är negativt.</span><span class="sxs-lookup"><span data-stu-id="cbacb-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>