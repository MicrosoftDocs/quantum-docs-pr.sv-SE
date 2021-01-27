---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: da901db2bb3c70186bfe0c8812b5710198d1dff3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844603"
---
# <a name="applytoeacha-operation"></a>ApplyToEachA-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en enskild qubit-åtgärd för varje-element i en register.
Modifieraren `A` anger att en qubit-åtgärd är adjointable.

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a>Indata

### <a name="singleelementoperation--t--unit--is-adj"></a>singleElementOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just just

Åtgärd att tillämpa på varje qubit.


### <a name="register--t"></a>Registrera: ' ' []

Matris för qubits som den aktuella åtgärden ska tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Målet som åtgärden agerar på.

## <a name="example"></a>Exempel

Förbered ett tre-qubit $ \ket{+} $-tillstånd:

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)