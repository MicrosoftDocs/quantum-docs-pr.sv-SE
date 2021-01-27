---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854677"
---
# <a name="measureallz-operation"></a>MeasureAllZ-åtgärd

Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


I gemensamma fall åtgärdas ett register över qubits i Pauli Z.

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>Description

Mäter ett register över qubits i $Z \otimes Z \otimes \cdots \otimes Z $, som representerar pariteten för hela registreringen.

## <a name="input"></a>Indata

### <a name="register--qubit"></a>Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registret som ska mätas.



## <a name="output--__invalidresult__"></a>Utdata: __ogiltig <Result>__

Resultatet av mätningen $Z \otimes Z \otimes \cdots \otimes Z $.