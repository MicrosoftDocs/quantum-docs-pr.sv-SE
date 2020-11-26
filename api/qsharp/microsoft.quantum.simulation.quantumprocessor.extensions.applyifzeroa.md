---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroA
title: ApplyIfZeroA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroA
qsharp.summary: ''
ms.openlocfilehash: d57f07beddc94d11a2143ba5d1fd975760260731
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230879"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="0eb00-102">ApplyIfZeroA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0eb00-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="0eb00-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="0eb00-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="0eb00-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0eb00-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="0eb00-105">Indata</span><span class="sxs-lookup"><span data-stu-id="0eb00-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="0eb00-106">measurementResult: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="0eb00-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj"></a><span data-ttu-id="0eb00-107">onResultZeroOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just</span><span class="sxs-lookup"><span data-stu-id="0eb00-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="0eb00-108">zeroArg: ' t</span><span class="sxs-lookup"><span data-stu-id="0eb00-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="0eb00-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0eb00-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0eb00-110">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="0eb00-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0eb00-111">Inte</span><span class="sxs-lookup"><span data-stu-id="0eb00-111">'T</span></span>

