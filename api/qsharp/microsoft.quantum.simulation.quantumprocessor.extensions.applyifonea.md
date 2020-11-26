---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneA
title: ApplyIfOneA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneA
qsharp.summary: ''
ms.openlocfilehash: 93a72ee7174b0022b1fe30cd779dfc57e96d8033
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228278"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="9086d-102">ApplyIfOneA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="9086d-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="9086d-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="9086d-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="9086d-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9086d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Adj), oneArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="9086d-105">Indata</span><span class="sxs-lookup"><span data-stu-id="9086d-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="9086d-106">measurementResult: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="9086d-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj"></a><span data-ttu-id="9086d-107">onResultOneOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just</span><span class="sxs-lookup"><span data-stu-id="9086d-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="9086d-108">oneArg: ' t</span><span class="sxs-lookup"><span data-stu-id="9086d-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="9086d-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9086d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9086d-110">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="9086d-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9086d-111">Inte</span><span class="sxs-lookup"><span data-stu-id="9086d-111">'T</span></span>

