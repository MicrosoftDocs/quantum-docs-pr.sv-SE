---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: b8b51e1c8d52c140c3ca1e5a54d0bd4cf4873046
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850842"
---
# <a name="applytoeachc-operation"></a>ApplyToEachC-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en enskild qubit-åtgärd för varje-element i en register.
Modifieraren `C` anger att en enskild-qubit-åtgärd är kontrollerbar.

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a>Indata

### <a name="singleelementoperation--t--unit--is-ctl"></a>singleElementOperation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL

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