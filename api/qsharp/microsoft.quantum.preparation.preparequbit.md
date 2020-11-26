---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: PrepareQubit-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  > [!WARNING]

  > PrepareQubit has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.


  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 84674d70d6a038ceaf1c637b22afa1b724d90795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193530"
---
# <a name="preparequbit-operation"></a>PrepareQubit-åtgärd

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> PrepareQubit är föråldrad. Använd <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> i stället.

Förbereder en qubit i eigenstate + 1 ( `Zero` ) för den aktuella Pauli-operatorn.
Om identitets operatören anges förbereds qubit i blandat läge för maximally.

Om qubit inlednings vis i $ \ket {0} $-tillstånd, förbereder den här åtgärden qubit i $ + $1-eigenstate för en specifik Pauli-operatör, eller, för `PauliI` , i maximally blandat tillstånd i stället (se <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Om qubit har varit i ett annat tillstånd än $ \ket {0} $, tillämpar den här åtgärden följande portar: $H $ för `PauliX` , $HS $ för `PauliY` , $I $ för `PauliZ` och <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` .

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a>Indata

### <a name="basis--pauli"></a>grund: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

En Pauli-operatör $P $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

En qubit som ska förberedas.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

