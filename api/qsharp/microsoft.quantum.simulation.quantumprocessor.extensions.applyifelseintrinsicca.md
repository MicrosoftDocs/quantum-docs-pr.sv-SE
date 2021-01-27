---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicCA
title: ApplyIfElseIntrinsicCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 6ba83f7344c77b95f2e7397cd42f39884556547a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855699"
---
# <a name="applyifelseintrinsicca-operation"></a><span data-ttu-id="b9e34-102">ApplyIfElseIntrinsicCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="b9e34-102">ApplyIfElseIntrinsicCA operation</span></span>

<span data-ttu-id="b9e34-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="b9e34-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="b9e34-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b9e34-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseIntrinsicCA (measurementResult : Result, onResultZeroOp : (Unit => Unit is Ctl + Adj), onResultOneOp : (Unit => Unit is Ctl + Adj)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b9e34-105">Indata</span><span class="sxs-lookup"><span data-stu-id="b9e34-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="b9e34-106">measurementResult: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="b9e34-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit--is-adj--ctl"></a><span data-ttu-id="b9e34-107">onResultZeroOp: [enhets](xref:microsoft.quantum.lang-ref.unit) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="b9e34-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onresultoneop--unit--unit--is-adj--ctl"></a><span data-ttu-id="b9e34-108">onResultOneOp: [enhets](xref:microsoft.quantum.lang-ref.unit) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="b9e34-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="b9e34-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b9e34-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

