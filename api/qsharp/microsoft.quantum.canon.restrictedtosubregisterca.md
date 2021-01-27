---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterCA
title: Funktionen RestrictedToSubregisterCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterCA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 9b1c8a6d1c843fb0533af16aafc4b3ca2ba2f0e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852178"
---
# <a name="restrictedtosubregisterca-function"></a>Funktionen RestrictedToSubregisterCA

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Begränsar en åtgärd till en matris med index i ett register, dvs. en under registrering.
Modifieraren `CA` anger att åtgärden är kontrollerbar och adjointable.

```qsharp
function RestrictedToSubregisterCA (op : (Qubit[] => Unit is Adj + Ctl), idxs : Int[]) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="op--qubit--unit--is-adj--ctl"></a>OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

Åtgärd som ska begränsas till en under registrering.


### <a name="idxs--int"></a>idxs: [int](xref:microsoft.quantum.lang-ref.int)[]

En matris med index som anger vilka qubits som åtgärden ska begränsas till.



## <a name="output--qubit--unit--is-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. RestrictedToSubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)