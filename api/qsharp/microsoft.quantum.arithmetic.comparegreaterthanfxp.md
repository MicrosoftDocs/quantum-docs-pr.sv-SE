---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: f49c713c8a1e8a6451f2c54fa59a72f00bfbb4c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843312"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="4031b-102">CompareGreaterThanFxP-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4031b-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="4031b-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4031b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4031b-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4031b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4031b-105">Jämför två tal med fasta punkter som lagras i Quantum-registren och styr en vändning på resultatet.</span><span class="sxs-lookup"><span data-stu-id="4031b-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4031b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4031b-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="4031b-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4031b-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4031b-108">Första fasta punkts nummer som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="4031b-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="4031b-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4031b-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4031b-110">Andra fasta punkts nummer som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="4031b-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="4031b-111">resultat: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4031b-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4031b-112">Resultatet av jämförelsen.</span><span class="sxs-lookup"><span data-stu-id="4031b-112">Result of the comparison.</span></span> <span data-ttu-id="4031b-113">Kommer att vändas om `fp1 > fp2` .</span><span class="sxs-lookup"><span data-stu-id="4031b-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4031b-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4031b-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4031b-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4031b-115">Remarks</span></span>

<span data-ttu-id="4031b-116">Den aktuella implementeringen kräver att de två fasta punkternas nummer har samma punkt position och samma antal qubits.</span><span class="sxs-lookup"><span data-stu-id="4031b-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>