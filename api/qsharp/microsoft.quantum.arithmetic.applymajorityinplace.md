---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: c32d7546fb753f78a72479cec11a6ed09c5e6179
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190742"
---
# <a name="applymajorityinplace-operation"></a>ApplyMajorityInPlace-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar den tre qubit majoritets åtgärden på plats i ett register över qubits.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

Den här åtgärden beräknar majoriteten av funktionerna på plats på 3 qubits.

Om vi betecknar utdata qubit som $z $ och indata-qubits som $x $ och $y $, utför åtgärden följande omvandling: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Indata

### <a name="output--qubit"></a>utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit för första indatamängden. Observera att utdata beräknas på plats och lagras i den här qubit.


### <a name="input--qubit"></a>inmatade: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Andra och tredje qubits för indatamängden.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

