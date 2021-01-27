---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneC
title: ApplyIfOneC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneC
qsharp.summary: ''
ms.openlocfilehash: ae6e0d16424e745303b377e70927cda847d2f1e8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858740"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="0f8b1-102">ApplyIfOneC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0f8b1-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="0f8b1-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="0f8b1-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="0f8b1-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0f8b1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneC<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl), oneArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="0f8b1-105">Indata</span><span class="sxs-lookup"><span data-stu-id="0f8b1-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="0f8b1-106">measurementResult: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="0f8b1-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-ctl"></a><span data-ttu-id="0f8b1-107">onResultOneOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="0f8b1-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="0f8b1-108">oneArg: ' t</span><span class="sxs-lookup"><span data-stu-id="0f8b1-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="0f8b1-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f8b1-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0f8b1-110">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="0f8b1-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0f8b1-111">Inte</span><span class="sxs-lookup"><span data-stu-id="0f8b1-111">'T</span></span>

