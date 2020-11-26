---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 36a5d585a493f0e6f33f74b1686aaa01cca7ac0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191048"
---
# <a name="addfxp-operation"></a><span data-ttu-id="8b1db-102">AddFxP-åtgärd</span><span class="sxs-lookup"><span data-stu-id="8b1db-102">AddFxP operation</span></span>

<span data-ttu-id="8b1db-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8b1db-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8b1db-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="8b1db-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="8b1db-105">Lägger till två värden för fasta punkter som lagras i Quantum-registren.</span><span class="sxs-lookup"><span data-stu-id="8b1db-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8b1db-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8b1db-106">Description</span></span>

<span data-ttu-id="8b1db-107">Med två register med fasta punkter i stat $ \ket{f_1} $ och $ \ket{f_2} $, utför åtgärden $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.</span><span class="sxs-lookup"><span data-stu-id="8b1db-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="8b1db-108">Indata</span><span class="sxs-lookup"><span data-stu-id="8b1db-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="8b1db-109">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="8b1db-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="8b1db-110">Första fasta punkts nummer</span><span class="sxs-lookup"><span data-stu-id="8b1db-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="8b1db-111">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="8b1db-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="8b1db-112">Det andra fasta punkt numret kommer att uppdateras så att det innehåller summan av de två indatana.</span><span class="sxs-lookup"><span data-stu-id="8b1db-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8b1db-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b1db-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8b1db-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="8b1db-114">Remarks</span></span>

<span data-ttu-id="8b1db-115">Den aktuella implementeringen kräver att två fasta nummer måste ha samma positions position i beräkningen från den minst signifikanta biten, d.v.s. $n _i $ och $p _i $ måste vara lika.</span><span class="sxs-lookup"><span data-stu-id="8b1db-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>