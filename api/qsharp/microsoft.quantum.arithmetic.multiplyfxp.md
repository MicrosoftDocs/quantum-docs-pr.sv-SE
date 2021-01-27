---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: MultiplyFxP-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 776ccb7a9e1ba1a34b28da6e1cf3a0aafe9da76b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843055"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="fbcc9-102">MultiplyFxP-åtgärd</span><span class="sxs-lookup"><span data-stu-id="fbcc9-102">MultiplyFxP operation</span></span>

<span data-ttu-id="fbcc9-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fbcc9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fbcc9-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="fbcc9-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="fbcc9-105">Multiplicerar två fasta nummer i Quantum-registren.</span><span class="sxs-lookup"><span data-stu-id="fbcc9-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fbcc9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="fbcc9-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="fbcc9-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="fbcc9-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="fbcc9-108">Första fasta punkts nummer.</span><span class="sxs-lookup"><span data-stu-id="fbcc9-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="fbcc9-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="fbcc9-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="fbcc9-110">Andra fasta punkt nummer.</span><span class="sxs-lookup"><span data-stu-id="fbcc9-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="fbcc9-111">resultat: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="fbcc9-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="fbcc9-112">Resulterande fast punkt nummer måste vara i tillstånd $ \ket {0} $ initialt.</span><span class="sxs-lookup"><span data-stu-id="fbcc9-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fbcc9-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fbcc9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fbcc9-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="fbcc9-114">Remarks</span></span>

<span data-ttu-id="fbcc9-115">För den aktuella implementeringen krävs tre fasta punkt nummer för samma punkt position och samma antal qubits.</span><span class="sxs-lookup"><span data-stu-id="fbcc9-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>