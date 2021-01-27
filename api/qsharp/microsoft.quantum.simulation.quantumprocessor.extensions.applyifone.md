---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOne
title: ApplyIfOne-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOne
qsharp.summary: ''
ms.openlocfilehash: fd5ee65615e4910d60db83cb8ec4201cfff9035d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855596"
---
# <a name="applyifone-operation"></a><span data-ttu-id="f3f5b-102">ApplyIfOne-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f3f5b-102">ApplyIfOne operation</span></span>

<span data-ttu-id="f3f5b-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="f3f5b-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="f3f5b-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f3f5b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOne<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="f3f5b-105">Indata</span><span class="sxs-lookup"><span data-stu-id="f3f5b-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="f3f5b-106">measurementResult: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="f3f5b-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit"></a><span data-ttu-id="f3f5b-107">onResultOneOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3f5b-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--t"></a><span data-ttu-id="f3f5b-108">oneArg: ' t</span><span class="sxs-lookup"><span data-stu-id="f3f5b-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="f3f5b-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3f5b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f3f5b-110">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f3f5b-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f3f5b-111">Inte</span><span class="sxs-lookup"><span data-stu-id="f3f5b-111">'T</span></span>

