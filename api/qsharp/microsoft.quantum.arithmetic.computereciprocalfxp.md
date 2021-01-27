---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843250"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="3d702-102">ComputeReciprocalFxP-åtgärd</span><span class="sxs-lookup"><span data-stu-id="3d702-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="3d702-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3d702-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3d702-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="3d702-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="3d702-105">Beräknar $1/x $ för ett fast punkt nummer $x $.</span><span class="sxs-lookup"><span data-stu-id="3d702-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3d702-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3d702-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="3d702-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="3d702-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="3d702-108">Fast punkts tal som ska inverteras.</span><span class="sxs-lookup"><span data-stu-id="3d702-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="3d702-109">resultat: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="3d702-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="3d702-110">Fast punkt nummer som ska innehålla resultatet.</span><span class="sxs-lookup"><span data-stu-id="3d702-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="3d702-111">Måste initieras till $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="3d702-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3d702-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3d702-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

