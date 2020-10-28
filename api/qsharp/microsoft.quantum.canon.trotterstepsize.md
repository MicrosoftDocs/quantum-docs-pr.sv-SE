---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: Funktionen TrotterStepSize
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: fabfbff74572b3c96c701de5443e4265a0468d78
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728296"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="3b9b1-102">Funktionen TrotterStepSize</span><span class="sxs-lookup"><span data-stu-id="3b9b1-102">TrotterStepSize function</span></span>

<span data-ttu-id="3b9b1-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3b9b1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3b9b1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b9b1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b9b1-105">Beräknar Trotter steg storlek i rekursiv implementering av algoritmen för simulering av Trotter.</span><span class="sxs-lookup"><span data-stu-id="3b9b1-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="3b9b1-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3b9b1-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="3b9b1-107">ordning: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3b9b1-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="3b9b1-108">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3b9b1-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="3b9b1-109">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3b9b1-109">Remarks</span></span>

<span data-ttu-id="3b9b1-110">Den här åtgärden använder en annan index konvention än för [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="3b9b1-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="3b9b1-111">Motsvarar i synnerhet `DecomposedIntoTimeStepsCA(_, 4)` den skalära $p _2 (\lambda) $ i Quant-pH/0508139.</span><span class="sxs-lookup"><span data-stu-id="3b9b1-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>