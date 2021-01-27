---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 44459e681daf1d28ce7d45f91ad59059babe5716
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853763"
---
# <a name="mresetx-operation"></a>MResetX-åtgärd

Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Mäter en enskild qubit i X-basen och återställer den till ett fast initialt tillstånd efter mätningen.

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a>Description

Utför en qubit-mätning i $X $-basis och säkerställer att qubit returneras till $ \ket {0} $ efter mätningen.

## <a name="input"></a>Indata

### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)

En enda qubit som ska mätas.



## <a name="output--__invalidresult__"></a>Utdata: __ogiltig <Result>__

Resultatet av att mäta `target` Pauli-$X $-basen.