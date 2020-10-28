---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733795"
---
# <a name="mresety-operation"></a>MResetY-åtgärd

Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)

Paketfilerna [](https://nuget.org/packages/)


Mäter en enskild qubit i Y-basen och återställer den till ett fast initialt tillstånd efter mätningen.

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a>Beskrivning

Utför en qubit-mätning i $Y $-basis och säkerställer att qubit returneras till $ \ket {0} $ efter mätningen.

## <a name="input"></a>Indata

### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)

En enda qubit som ska mätas.



## <a name="output--__invalidresult__"></a>Utdata: __ogiltig <Result>__

Resultatet av att mäta `target` Pauli-$Y $-basen.