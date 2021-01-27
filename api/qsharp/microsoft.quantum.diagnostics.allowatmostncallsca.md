---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853539"
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



## <a name="example"></a>Exempel

Följande fragment fungerar inte när de körs på datorer som har stöd för den här diagnostiken:

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a>Kommentarer

Den här åtgärden kan ersättas av en no-op på mål som inte stöder den.