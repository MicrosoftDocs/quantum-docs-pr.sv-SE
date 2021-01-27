---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRA
title: ApplyIfElseRA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRA
qsharp.summary: ''
ms.openlocfilehash: 11427026d66fc6f46f05004db4dae6f9fa05d921
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855666"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="e0946-102">ApplyIfElseRA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e0946-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="e0946-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="e0946-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="e0946-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e0946-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseRA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj), oneArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="e0946-105">Indata</span><span class="sxs-lookup"><span data-stu-id="e0946-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="e0946-106">measurementResult: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="e0946-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj"></a><span data-ttu-id="e0946-107">onResultZeroOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just</span><span class="sxs-lookup"><span data-stu-id="e0946-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="e0946-108">zeroArg: ' t</span><span class="sxs-lookup"><span data-stu-id="e0946-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit--is-adj"></a><span data-ttu-id="e0946-109">onResultOneOp: ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="e0946-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onearg--u"></a><span data-ttu-id="e0946-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="e0946-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="e0946-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e0946-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e0946-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="e0946-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e0946-113">Inte</span><span class="sxs-lookup"><span data-stu-id="e0946-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="e0946-114">' U</span><span class="sxs-lookup"><span data-stu-id="e0946-114">'U</span></span>

