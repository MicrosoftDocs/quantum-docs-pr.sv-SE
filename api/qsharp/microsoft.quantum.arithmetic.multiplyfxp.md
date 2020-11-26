---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: MultiplyFxP-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 3c9ef9ade660e1f420d85162104d773b96722eeb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222617"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="cf68a-102">MultiplyFxP-åtgärd</span><span class="sxs-lookup"><span data-stu-id="cf68a-102">MultiplyFxP operation</span></span>

<span data-ttu-id="cf68a-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cf68a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cf68a-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="cf68a-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="cf68a-105">Multiplicerar två fasta nummer i Quantum-registren.</span><span class="sxs-lookup"><span data-stu-id="cf68a-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cf68a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="cf68a-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="cf68a-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="cf68a-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="cf68a-108">Första fasta punkts nummer.</span><span class="sxs-lookup"><span data-stu-id="cf68a-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="cf68a-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="cf68a-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="cf68a-110">Andra fasta punkt nummer.</span><span class="sxs-lookup"><span data-stu-id="cf68a-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="cf68a-111">resultat: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="cf68a-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="cf68a-112">Resulterande fast punkt nummer måste vara i tillstånd $ \ket {0} $ initialt.</span><span class="sxs-lookup"><span data-stu-id="cf68a-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cf68a-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf68a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cf68a-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="cf68a-114">Remarks</span></span>

<span data-ttu-id="cf68a-115">För den aktuella implementeringen krävs tre fasta punkt nummer för samma punkt position och samma antal qubits.</span><span class="sxs-lookup"><span data-stu-id="cf68a-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>