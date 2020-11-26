---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: ApplyConditionallyA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: 8117fd632b78c24c9ecb8545274eaf296645b645
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230420"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="88e03-102">ApplyConditionallyA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="88e03-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="88e03-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="88e03-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="88e03-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="88e03-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="88e03-105">Indata</span><span class="sxs-lookup"><span data-stu-id="88e03-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="88e03-106">measurementResults: __ogiltig <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="88e03-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="88e03-107">resultsValues: __ogiltig <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="88e03-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj"></a><span data-ttu-id="88e03-108">onEqualOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just</span><span class="sxs-lookup"><span data-stu-id="88e03-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="88e03-109">equalArg: ' t</span><span class="sxs-lookup"><span data-stu-id="88e03-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj"></a><span data-ttu-id="88e03-110">onNonEqualOp: ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="88e03-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="88e03-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="88e03-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="88e03-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="88e03-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="88e03-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="88e03-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="88e03-114">Inte</span><span class="sxs-lookup"><span data-stu-id="88e03-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="88e03-115">' U</span><span class="sxs-lookup"><span data-stu-id="88e03-115">'U</span></span>

