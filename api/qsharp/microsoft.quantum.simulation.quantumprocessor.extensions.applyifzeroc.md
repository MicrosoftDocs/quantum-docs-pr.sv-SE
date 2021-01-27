---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: ApplyIfZeroC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: c4d1618ff5e2a3d61823eddd6905445effcecfdd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854174"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="5fc4a-102">ApplyIfZeroC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5fc4a-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="5fc4a-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="5fc4a-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="5fc4a-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5fc4a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="5fc4a-105">Indata</span><span class="sxs-lookup"><span data-stu-id="5fc4a-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="5fc4a-106">measurementResult: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="5fc4a-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="5fc4a-107">onResultZeroOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="5fc4a-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="5fc4a-108">zeroArg: ' t</span><span class="sxs-lookup"><span data-stu-id="5fc4a-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="5fc4a-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fc4a-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5fc4a-110">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="5fc4a-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5fc4a-111">Inte</span><span class="sxs-lookup"><span data-stu-id="5fc4a-111">'T</span></span>

