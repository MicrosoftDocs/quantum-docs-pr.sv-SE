---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 04fb0f84ddf79a3d2cfc21fdaabd16c129f6d72f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194210"
---
# <a name="mresetx-operation"></a>MResetX-åtgärd

Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Mäter en enskild qubit i X-basen och återställer den till ett fast initialt tillstånd efter mätningen.

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a>Beskrivning

Utför en qubit-mätning i $X $-basis och säkerställer att qubit returneras till $ \ket {0} $ efter mätningen.

## <a name="input"></a>Indata

### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)

En enda qubit som ska mätas.



## <a name="output--__invalidresult__"></a>Utdata: __ogiltig <Result>__

Resultatet av att mäta `target` Pauli-$X $-basen.