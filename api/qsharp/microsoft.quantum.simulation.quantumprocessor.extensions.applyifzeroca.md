---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: ApplyIfZeroCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: f7dd30171acd3786c6d012b82b9abf99f9042caf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858255"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="bf7dd-102">ApplyIfZeroCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="bf7dd-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="bf7dd-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="bf7dd-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="bf7dd-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bf7dd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bf7dd-105">Indata</span><span class="sxs-lookup"><span data-stu-id="bf7dd-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="bf7dd-106">measurementResult: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="bf7dd-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="bf7dd-107">onResultZeroOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="bf7dd-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="bf7dd-108">zeroArg: ' t</span><span class="sxs-lookup"><span data-stu-id="bf7dd-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="bf7dd-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf7dd-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bf7dd-110">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="bf7dd-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bf7dd-111">Inte</span><span class="sxs-lookup"><span data-stu-id="bf7dd-111">'T</span></span>

