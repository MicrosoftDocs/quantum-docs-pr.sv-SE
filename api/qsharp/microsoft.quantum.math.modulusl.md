---
uid: Microsoft.Quantum.Math.ModulusL
title: Modulus-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842748"
---
# <a name="modulusl-function"></a><span data-ttu-id="a7d8c-102">Modulus-funktion</span><span class="sxs-lookup"><span data-stu-id="a7d8c-102">ModulusL function</span></span>

<span data-ttu-id="a7d8c-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a7d8c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a7d8c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7d8c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7d8c-105">Beräknar de kanoniska resterna av `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="a7d8c-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="a7d8c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a7d8c-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="a7d8c-107">värde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a7d8c-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a7d8c-108">Värdet för vilken restsubstanser beräknas</span><span class="sxs-lookup"><span data-stu-id="a7d8c-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="a7d8c-109">Modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a7d8c-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a7d8c-110">Den modul som rester tar emot måste vara positiva</span><span class="sxs-lookup"><span data-stu-id="a7d8c-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="a7d8c-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a7d8c-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a7d8c-112">Heltal $r $ mellan 0 och `modulus - 1` som `value - r` är delbar med modulus</span><span class="sxs-lookup"><span data-stu-id="a7d8c-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="a7d8c-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a7d8c-113">Remarks</span></span>

<span data-ttu-id="a7d8c-114">Den här funktionen fungerar annorlunda för hur operatorn `%` beter sig i C# och Q # som i resultatet är alltid ett icke-negativt heltal mellan 0 och `modulus - 1` , även om värdet är negativt.</span><span class="sxs-lookup"><span data-stu-id="a7d8c-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>