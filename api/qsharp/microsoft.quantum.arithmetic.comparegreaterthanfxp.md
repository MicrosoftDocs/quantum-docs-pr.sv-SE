---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: 1e9afc7645f62b932fa8ebc3d33e21a2a5182361
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223535"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="7d596-102">CompareGreaterThanFxP-åtgärd</span><span class="sxs-lookup"><span data-stu-id="7d596-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="7d596-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7d596-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7d596-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="7d596-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="7d596-105">Jämför två tal med fasta punkter som lagras i Quantum-registren och styr en vändning på resultatet.</span><span class="sxs-lookup"><span data-stu-id="7d596-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7d596-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7d596-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="7d596-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="7d596-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="7d596-108">Första fasta punkts nummer som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="7d596-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="7d596-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="7d596-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="7d596-110">Andra fasta punkts nummer som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="7d596-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="7d596-111">resultat: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7d596-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7d596-112">Resultatet av jämförelsen.</span><span class="sxs-lookup"><span data-stu-id="7d596-112">Result of the comparison.</span></span> <span data-ttu-id="7d596-113">Kommer att vändas om `fp1 > fp2` .</span><span class="sxs-lookup"><span data-stu-id="7d596-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d596-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d596-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7d596-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="7d596-115">Remarks</span></span>

<span data-ttu-id="7d596-116">Den aktuella implementeringen kräver att de två fasta punkternas nummer har samma punkt position och samma antal qubits.</span><span class="sxs-lookup"><span data-stu-id="7d596-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>