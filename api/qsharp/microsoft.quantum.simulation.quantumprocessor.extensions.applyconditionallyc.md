---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: ApplyConditionallyC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: 09496d384a70fa9fb6826304ce9909034297a118
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847861"
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

