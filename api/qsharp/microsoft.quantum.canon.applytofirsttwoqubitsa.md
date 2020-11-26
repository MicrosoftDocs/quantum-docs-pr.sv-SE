---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: ApplyToFirstTwoQubitsA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 1a286c167a87372dc89d62ab3733b186298c43a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208711"
---
# <a name="applytofirsttwoqubitsa-operation"></a>ApplyToFirstTwoQubitsA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en åtgärd på de två första qubits i registret.
Modifieraren `A` anger att åtgärden är adjointable.

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Indata

### <a name="op--qubitqubit--unit--is-adj"></a>OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

En åtgärd som ska tillämpas på de två första qubits


### <a name="register--qubit"></a>Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit-matrisen till de två första qubits som åtgärden tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Detta motsvarar:

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyToFirstTwoQubits](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)