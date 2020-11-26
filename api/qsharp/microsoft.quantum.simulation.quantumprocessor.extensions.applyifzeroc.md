---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: ApplyIfZeroC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: 9a73ea9ec607bec89c996c096b235a72185b453d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230845"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="cfbe0-102">ApplyIfZeroC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="cfbe0-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="cfbe0-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="cfbe0-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="cfbe0-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cfbe0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="cfbe0-105">Indata</span><span class="sxs-lookup"><span data-stu-id="cfbe0-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="cfbe0-106">measurementResult: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="cfbe0-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="cfbe0-107">onResultZeroOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="cfbe0-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="cfbe0-108">zeroArg: ' t</span><span class="sxs-lookup"><span data-stu-id="cfbe0-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="cfbe0-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cfbe0-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cfbe0-110">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="cfbe0-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cfbe0-111">Inte</span><span class="sxs-lookup"><span data-stu-id="cfbe0-111">'T</span></span>

