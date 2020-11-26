---
uid: Microsoft.Quantum.Math.ModulusI
title: Modulus-funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6bbb3877b93e1fc6b38f85a716ba617311c7cfba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227785"
---
# <a name="modulusi-function"></a><span data-ttu-id="6a7bc-102">Modulus-funktion</span><span class="sxs-lookup"><span data-stu-id="6a7bc-102">ModulusI function</span></span>

<span data-ttu-id="6a7bc-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6a7bc-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6a7bc-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6a7bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6a7bc-105">Beräknar de kanoniska resterna av `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="6a7bc-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="6a7bc-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6a7bc-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="6a7bc-107">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a7bc-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a7bc-108">Värdet för vilken restsubstanser beräknas</span><span class="sxs-lookup"><span data-stu-id="6a7bc-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="6a7bc-109">Modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a7bc-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a7bc-110">Den modul som rester tar emot måste vara positiva</span><span class="sxs-lookup"><span data-stu-id="6a7bc-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="6a7bc-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a7bc-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a7bc-112">Heltal $r $ mellan 0 och `modulus - 1` som `value - r` är delbar med modulus</span><span class="sxs-lookup"><span data-stu-id="6a7bc-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="6a7bc-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6a7bc-113">Remarks</span></span>

<span data-ttu-id="6a7bc-114">Den här funktionen fungerar annorlunda för hur operatorn `%` beter sig i C# och Q # som i resultatet är alltid ett positivt heltal mellan 0 och `modulus - 1` , även om värdet är negativt.</span><span class="sxs-lookup"><span data-stu-id="6a7bc-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>