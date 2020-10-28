---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733603"
---
# <a name="settobasisstate-operation"></a>SetToBasisState-åtgärd

Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)

Paketfilerna [](https://nuget.org/packages/)


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