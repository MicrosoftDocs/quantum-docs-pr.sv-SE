---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: dfa054360a5e82b7ae6ec5a6d52e7d5fe566f42e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854631"
---
# <a name="settobasisstate-operation"></a>SetToBasisState-åtgärd

Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Ställer in en qubit till ett angivet beräknings underlag genom att mäta qubit och tillämpa en bit-flip vid behov.

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a>Indata

### <a name="desired--__invalidresult__"></a>önskad: __ogiltig <Result>__

Det bas tillstånd som qubit ska vara inställt på.


### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit vars tillstånd ska anges.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Som en invariant av den här åtgärden, anropas `M(q)` omedelbart efter `SetToBasisState(result, q)` att det returneras `result` .