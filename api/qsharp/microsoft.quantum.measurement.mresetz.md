---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 494f11c8129175ddd84c6539f5e9df1a758e8a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194142"
---
# <a name="mresetz-operation"></a>MResetZ-åtgärd

Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Mäter en enskild qubit i Z-basen och återställer den till ett fast initialt tillstånd efter mätningen.

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a>Beskrivning

Utför en qubit-mätning i $Z $-basis och säkerställer att qubit returneras till $ \ket {0} $ efter mätningen.

## <a name="input"></a>Indata

### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)

En enda qubit som ska mätas.



## <a name="output--__invalidresult__"></a>Utdata: __ogiltig <Result>__

Resultatet av att mäta `target` Pauli-$Z $-basen.