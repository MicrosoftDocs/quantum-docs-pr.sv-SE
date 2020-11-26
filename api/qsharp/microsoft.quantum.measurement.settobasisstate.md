---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194159"
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