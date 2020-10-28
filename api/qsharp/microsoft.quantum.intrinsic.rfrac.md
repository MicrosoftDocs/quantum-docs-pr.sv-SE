---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: RFrac-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: 9fe6aee6c7bb9e52538eae5d2caa2a6025cb85d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732939"
---
# <a name="rfrac-operation"></a>RFrac-åtgärd

Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)

Paketfilerna [](https://nuget.org/packages/)


Använder en rotation om den angivna Pauli-axeln med en vinkel angiven som en dyadic fraktion.

\begin{align} R_ {\mu} (n, k) \mathrel{: =} e ^ {i \pi n \ sigma_ {\mu}/2 ^ k}, \end{align} där $ \mu \in \{ i, X, Y, Z \} $.

> [!WARNING]
> Den här åtgärden använder **motsatt** inloggnings konvention från @"microsoft.quantum.intrinsic.r" .

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a>Indata

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli-operatorn ska vara exponentiated för att forma rotationen.


### <a name="numerator--int"></a>täljare: [int](xref:microsoft.quantum.lang-ref.int)

Täljare i dyadic fraktions representation av den vinkel som qubit ska roteras med.


### <a name="power--int"></a>effekt: [int](xref:microsoft.quantum.lang-ref.int)

Kraften hos två anger nämnaren för den vinkel som qubit ska roteras med.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit som porten ska tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Motsvarar:

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```