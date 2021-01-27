---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: PreparePauliEigenstate-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: 473bb2fa4429a14f69bcae4573354aad87dc37df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854343"
---
# <a name="preparepaulieigenstate-operation"></a>PreparePauliEigenstate-åtgärd

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Förbereder en qubit i positiv eigenstate för en specifik Pauli-operator.
Om identitets operatören anges förbereds qubit i blandat läge för maximally.

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a>Description

Om qubit inlednings vis i $ \ket {0} $-tillstånd, förbereder den här åtgärden qubit i $ + $1-eigenstate för en specifik Pauli-operatör, eller, för `PauliI` , i maximally blandat tillstånd i stället (se <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Om qubit har varit i ett annat tillstånd än $ \ket {0} $, tillämpar den här åtgärden följande portar: $H $ för `PauliX` , $HS $ för `PauliY` , $I $ för `PauliZ` och <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` .

## <a name="input"></a>Indata

### <a name="basis--pauli"></a>grund: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

En Pauli-operatör $P $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

En qubit som ska förberedas.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exempel

Så här förbereder du en qubit i $ \ket{+} $ State:

```qsharp
using (q = Qubit()) {
    PreparePauliEigenstate(PauliX, qubit);
    // ...
}
```