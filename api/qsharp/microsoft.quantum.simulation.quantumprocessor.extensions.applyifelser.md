---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: ApplyIfElseR-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: 9e391b61aa4d22ad02bf657a866f959d35b6628f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192680"
---
# <a name="applyifelser-operation"></a>ApplyIfElseR-åtgärd

Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a>Indata

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __ogiltig <Result>__




### <a name="onresultzeroop--t--unit"></a>onResultZeroOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit) 




### <a name="zeroarg--t"></a>zeroArg: ' t




### <a name="onresultoneop--u--unit"></a>onResultOneOp: ' U => [enhet](xref:microsoft.quantum.lang-ref.unit) 




### <a name="onearg--u"></a>oneArg: ' U





## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte


### <a name="u"></a>' U

