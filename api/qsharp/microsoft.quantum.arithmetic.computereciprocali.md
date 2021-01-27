---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: ComputeReciprocalI-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: c28027f7a2533885102a54a028bec37eb608f2b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846710"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="4af02-102">ComputeReciprocalI-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4af02-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="4af02-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4af02-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4af02-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4af02-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4af02-105">Beräknar motsvarande 1/x för ett osignerat heltal x med hjälp av heltals division.</span><span class="sxs-lookup"><span data-stu-id="4af02-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="4af02-106">Resultatet, som tolkas som ett heltal, blir `floor(2^(2*n-1) / x)` .</span><span class="sxs-lookup"><span data-stu-id="4af02-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4af02-107">Indata</span><span class="sxs-lookup"><span data-stu-id="4af02-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="4af02-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4af02-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4af02-109">n-bitars osignerat heltal</span><span class="sxs-lookup"><span data-stu-id="4af02-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="4af02-110">resultat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4af02-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4af02-111">2N-bitars utdata måste vara i $ \ket {0} $ inlednings vis.</span><span class="sxs-lookup"><span data-stu-id="4af02-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4af02-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4af02-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4af02-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4af02-113">Remarks</span></span>

<span data-ttu-id="4af02-114">För indata x = 0 blir utdata alla.</span><span class="sxs-lookup"><span data-stu-id="4af02-114">For the input x=0, the output will be all-ones.</span></span>