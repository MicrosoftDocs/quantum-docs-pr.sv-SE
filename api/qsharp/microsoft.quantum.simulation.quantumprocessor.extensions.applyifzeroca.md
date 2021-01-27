---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: ApplyIfZeroCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: f7dd30171acd3786c6d012b82b9abf99f9042caf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858255"
---
# <a name="applyifzeroca-operation"></a>ApplyIfZeroCA-åtgärd

Namnrymd: [Microsoft. Quantum. simulering. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __ogiltig <Result>__




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a>onResultZeroOp: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL




### <a name="zeroarg--t"></a>zeroArg: ' t





## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

