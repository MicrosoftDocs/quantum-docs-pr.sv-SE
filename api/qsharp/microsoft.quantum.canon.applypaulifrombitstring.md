---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: ApplyPauliFromBitString-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: cf4c99ec5134fac788cdd4c8a057258790152a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209068"
---
# <a name="applypaulifrombitstring-operation"></a>ApplyPauliFromBitString-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Använder en Pauli-operator för varje qubit i en matris om motsvarande bit i en boolesk matris matchar ett angivet inflöde.

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli-operatör som ska gälla för `qubits[idx]` var `bitsApply == bits[idx]`


### <a name="bitapply--bool"></a>bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)

Använd Pauli om biten är det här värdet


### <a name="bits--bool"></a>bitar: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Booleskt register som anger vilka motsvarande qubit i som `qubits` ska användas


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Quantum register som den angivna Pauli-operatorn ska tillämpas på selektivt



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Den booleska matrisen och Quantum-registret måste vara lika långa.