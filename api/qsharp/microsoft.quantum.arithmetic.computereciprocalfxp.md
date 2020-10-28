---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: e8f31d82fc69a3d7f4b571c4a679255dffc28b7f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731603"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="ad22e-102">ComputeReciprocalFxP-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ad22e-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="ad22e-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ad22e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ad22e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ad22e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ad22e-105">Beräknar $1/x $ för ett fast punkt nummer $x $.</span><span class="sxs-lookup"><span data-stu-id="ad22e-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="ad22e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ad22e-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="ad22e-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="ad22e-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="ad22e-108">Fast punkts tal som ska inverteras.</span><span class="sxs-lookup"><span data-stu-id="ad22e-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="ad22e-109">resultat: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="ad22e-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="ad22e-110">Fast punkt nummer som ska innehålla resultatet.</span><span class="sxs-lookup"><span data-stu-id="ad22e-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="ad22e-111">Måste initieras till $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="ad22e-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad22e-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad22e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

