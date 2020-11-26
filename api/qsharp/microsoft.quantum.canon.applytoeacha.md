---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9819e78760caf6180edc5c2ca5e402060e3029a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217806"
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

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)