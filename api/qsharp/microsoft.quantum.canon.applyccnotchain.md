---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: ApplyCCNOTChain-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: 275f31ea636d15eb0d78e5148e8af6b58d22729d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209663"
---
# <a name="applyccnotchain-operation"></a>ApplyCCNOTChain-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementerar en överlappande av CCNOT-grindar som styrs på motsvarande bitar av två qubit-register, och fungerar på nästa qubit i en av registren.
Från qubits vid position 0 i båda registren register som kontroller, tillämpas CCNOT på qubit vid position 1 i mål registret, och styrs sedan av qubits vid position 1 på qubit vid position 2 i mål registret, osv., som avslutas med en åtgärd på mål qubit i position `Length(nQubits)-1` .

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="register--qubit"></a>Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit-registrering, används endast för kontroller.


### <a name="targets--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit-register som används för kontroller och som mål.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Mål qubit-registret måste ha en qubit över det andra registret.