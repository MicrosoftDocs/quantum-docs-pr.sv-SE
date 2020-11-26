---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: ApplyIfZeroCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: accc3ca9c0d99c48c713333ce1cc907054c2a860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230794"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="e3327-102">ApplyIfZeroCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e3327-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="e3327-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="e3327-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="e3327-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e3327-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e3327-105">Indata</span><span class="sxs-lookup"><span data-stu-id="e3327-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="e3327-106">measurementResult: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="e3327-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="e3327-107">onResultZeroOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="e3327-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="e3327-108">zeroArg: ' t</span><span class="sxs-lookup"><span data-stu-id="e3327-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="e3327-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3327-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e3327-110">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="e3327-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e3327-111">Inte</span><span class="sxs-lookup"><span data-stu-id="e3327-111">'T</span></span>

