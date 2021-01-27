---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: PrepareQubit-åtgärd
ms.date: 1/23/2021 12:00:00 AM
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
ms.openlocfilehash: e6a88ccf4c01b2f0a7344e3823b2748790cf9650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854338"
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

