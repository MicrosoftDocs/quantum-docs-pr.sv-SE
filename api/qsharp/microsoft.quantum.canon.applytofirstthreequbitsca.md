---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: ApplyToFirstThreeQubitsCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 7e090a116a63e26278b05dc7c2fda9b65ff15bae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208796"
---
# <a name="applytofirstthreequbitsca-operation"></a>ApplyToFirstThreeQubitsCA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en åtgärd på de första tre qubits i registret.
Modifieraren `CA` anger att åtgärden är kontrollerbar och adjointable.

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="op--qubitqubitqubit--unit--is-adj--ctl"></a>OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En åtgärd som ska tillämpas på de första tre qubits


### <a name="register--qubit"></a>Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit-matrisen till de tre första qubits som åtgärden tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Detta motsvarar:

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyToFirstThreeQubits](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)