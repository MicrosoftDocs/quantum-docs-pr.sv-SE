---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsic
title: ApplyConditionallyIntrinsic-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsic
qsharp.summary: ''
ms.openlocfilehash: 2301ef25a262ead63c3550777af79e1d3f9c5a98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858479"
---
# <a name="applyconditionallyintrinsic-operation"></a><span data-ttu-id="6fece-102">ApplyConditionallyIntrinsic-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6fece-102">ApplyConditionallyIntrinsic operation</span></span>

<span data-ttu-id="6fece-103">Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="6fece-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="6fece-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6fece-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyIntrinsic (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit), onNonEqualOp : (Unit => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="6fece-105">Indata</span><span class="sxs-lookup"><span data-stu-id="6fece-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="6fece-106">measurementResults: __ogiltig <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="6fece-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="6fece-107">resultsValues: __ogiltig <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="6fece-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--unit--unit"></a><span data-ttu-id="6fece-108">onEqualOp: [enhets](xref:microsoft.quantum.lang-ref.unit) => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6fece-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onnonequalop--unit--unit"></a><span data-ttu-id="6fece-109">onNonEqualOp: [enhets](xref:microsoft.quantum.lang-ref.unit) => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6fece-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="6fece-110">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6fece-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

