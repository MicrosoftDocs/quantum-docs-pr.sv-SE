---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicA
title: ApplyConditionallyIntrinsicA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicA
qsharp.summary: ''
ms.openlocfilehash: b22cb94a835f0504116e7152a4a1bfe66c483c10
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858522"
---
# <a name="applyconditionallyintrinsica-operation"></a><span data-ttu-id="a9488-102">ApplyConditionallyIntrinsicA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a9488-102">ApplyConditionallyIntrinsicA operation</span></span>

<span data-ttu-id="a9488-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="a9488-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="a9488-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a9488-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Adj), onNonEqualOp : (Unit => Unit is Adj)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="a9488-105">Indata</span><span class="sxs-lookup"><span data-stu-id="a9488-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="a9488-106">measurementResults: __ogiltig <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="a9488-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="a9488-107">resultsValues: __ogiltig <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="a9488-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--unit--unit--is-adj"></a><span data-ttu-id="a9488-108">onEqualOp: [enhets](xref:microsoft.quantum.lang-ref.unit) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="a9488-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onnonequalop--unit--unit--is-adj"></a><span data-ttu-id="a9488-109">onNonEqualOp: [enhets](xref:microsoft.quantum.lang-ref.unit) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="a9488-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="a9488-110">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9488-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

