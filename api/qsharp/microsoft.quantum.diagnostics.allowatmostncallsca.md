---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 7caf33e33318bb74cb160436940eff9f0f2782cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202574"
---
# <a name="allowatmostncallsca-operation"></a>AllowAtMostNCallsCA-åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mellan ett anrop till den här åtgärden och dess intilliggande, förutsätter att en viss åtgärd anropas högst ett visst antal gånger.

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a>Indata

### <a name="ntimes--int"></a>nTimes: [int](xref:microsoft.quantum.lang-ref.int)

Det maximala antalet gånger som `op` kan anropas.


### <a name="op--tinput--toutput--is-adj--ctl"></a>OP: ' TInput => ' TOutput är just + CTL

En åtgärd vars anrop ska begränsas.


### <a name="message--string"></a>meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)

Ett meddelande som ska visas vid fel.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>'TOutput



## <a name="remarks"></a>Kommentarer

Den här åtgärden kan ersättas av en no-op på mål som inte stöder den.