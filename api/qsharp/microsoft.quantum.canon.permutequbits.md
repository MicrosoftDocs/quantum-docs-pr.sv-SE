---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 2fbbe0d99ad1383d77cb08ff6b03bcebd8a1971f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852330"
---
# <a name="permutequbits-operation"></a>PermuteQubits-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permutes qubits med hjälp av VÄXLINGs åtgärden.

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="ordering--int"></a>ordning: [int](xref:microsoft.quantum.lang-ref.int)[]

Beskriver den nya ordningen för qubits där qubit vid indexet nu kommer att behållas [i].


### <a name="register--qubit"></a>Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit-register att du ska handla på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exempel

Order = [2, 1, 0] och registrera $ \ket{\ alpha_0} \ket{\ alpha_1} \ket{\ alpha_2} $, PermuteQubits ändrar registret till $ \ket{\ alpha_2} \ket{\ alpha_1} \ket{\ alpha_0} $

```qsharp
// The following two lines are equivalent
PermuteQubits([2, 1, 0], register);
SWAP(register[0], register[2]);
```