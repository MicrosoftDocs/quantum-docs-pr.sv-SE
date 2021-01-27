---
uid: Microsoft.Quantum.Canon.RAll1
title: RAll1-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: f4159a6cc0e0b4f18f418a53a309b5ce527b2608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852265"
---
# <a name="rall1-operation"></a>RAll1-åtgärd

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utför en fas växlings åtgärd.

$R = \boldone-(1-e ^ {i \phi}) \ket{1\cdots 1} \bra{1\cdots 1} $.

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="phase--double"></a>fas: [dubbel](xref:microsoft.quantum.lang-ref.double)

Fasen $ \phi $ som tillämpas på tillstånd $ \ket{1\cdots 1} \bra{1\cdots 1} $.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registret vars tillstånd ska roteras med $R $.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

