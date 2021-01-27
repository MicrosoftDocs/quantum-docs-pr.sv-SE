---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: Funktionen RestrictedToSubregisterA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: c260a0e422d7ffb8137f6ac41e1cb398b2f4a2a7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852184"
---
# <a name="restrictedtosubregistera-function"></a>Funktionen RestrictedToSubregisterA

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Begränsar en åtgärd till en matris med index i ett register, dvs. en under registrering.
Modifieraren `A` anger att åtgärden är adjointable.

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a>Indata

### <a name="op--qubit--unit--is-adj"></a>OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

Åtgärd som ska begränsas till en under registrering.


### <a name="idxs--int"></a>idxs: [int](xref:microsoft.quantum.lang-ref.int)[]

En matris med index som anger vilka qubits som åtgärden ska begränsas till.



## <a name="output--qubit--unit--is-adj"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = just> [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. RestrictedToSubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)