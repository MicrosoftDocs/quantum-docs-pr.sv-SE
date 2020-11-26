---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: ApplyConditionallyC-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: 963a85e0e442592c01a2e70fa0dc02d6048d8be7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229043"
---
# <a name="applyconditionallyc-operation"></a>ApplyConditionallyC-åtgärd

Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit is Ctl
```


## <a name="input"></a>Indata

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __ogiltig <Result>__[]




### <a name="resultsvalues--__invalidresult__"></a>resultsValues: __ogiltig <Result>__[]




### <a name="onequalop--t--unit--is-ctl"></a>onEqualOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL




### <a name="equalarg--t"></a>equalArg: ' t




### <a name="onnonequalop--u--unit--is-ctl"></a>onNonEqualOp: ' U => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL




### <a name="nonequalarg--u"></a>nonEqualArg: ' U





## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte


### <a name="u"></a>' U

