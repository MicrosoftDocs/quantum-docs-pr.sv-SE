---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZero
title: ApplyIfZero-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZero
qsharp.summary: ''
ms.openlocfilehash: a76c6269ac4445326ac357fe2cdd552847089a6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732467"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="e98c1-102">ApplyIfZero-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e98c1-102">ApplyIfZero operation</span></span>

<span data-ttu-id="e98c1-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="e98c1-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="e98c1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e98c1-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZero<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="e98c1-105">Indata</span><span class="sxs-lookup"><span data-stu-id="e98c1-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="e98c1-106">measurementResult: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="e98c1-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="e98c1-107">onResultZeroOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e98c1-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="e98c1-108">zeroArg: ' t</span><span class="sxs-lookup"><span data-stu-id="e98c1-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="e98c1-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e98c1-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e98c1-110">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="e98c1-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e98c1-111">Inte</span><span class="sxs-lookup"><span data-stu-id="e98c1-111">'T</span></span>

