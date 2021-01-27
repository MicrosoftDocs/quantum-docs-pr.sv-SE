---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: ApplyToEachIndexC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: c005f616d580438891fbcb9f3c727b8e961e138d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850811"
---
# <a name="applytoeachindexc-operation"></a>ApplyToEachIndexC-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tillämpar en enskild qubit-åtgärd på varje indexerat element i en register.
Modifieraren `C` anger att en enskild-qubit-åtgärd är kontrollerbar.

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a>Indata

### <a name="singleelementoperation--intt--unit--is-ctl"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är CTL

Åtgärd att tillämpa på varje qubit.


### <a name="register--t"></a>Registrera: ' ' []

Matris för qubits som den aktuella åtgärden ska tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Målet som varje åtgärd agerar på.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)