---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOne
title: ApplyIfOne-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOne
qsharp.summary: ''
ms.openlocfilehash: 0a844e0cd8b4faaa28037985918a4d2d187ebc1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732099"
---
# <a name="applyifone-operation"></a><span data-ttu-id="3840d-102">ApplyIfOne-åtgärd</span><span class="sxs-lookup"><span data-stu-id="3840d-102">ApplyIfOne operation</span></span>

<span data-ttu-id="3840d-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="3840d-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="3840d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3840d-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOne<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="3840d-105">Indata</span><span class="sxs-lookup"><span data-stu-id="3840d-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="3840d-106">measurementResult: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="3840d-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit"></a><span data-ttu-id="3840d-107">onResultOneOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3840d-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--t"></a><span data-ttu-id="3840d-108">oneArg: ' t</span><span class="sxs-lookup"><span data-stu-id="3840d-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="3840d-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3840d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3840d-110">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="3840d-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3840d-111">Inte</span><span class="sxs-lookup"><span data-stu-id="3840d-111">'T</span></span>

