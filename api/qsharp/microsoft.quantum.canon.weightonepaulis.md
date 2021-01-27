---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: Funktionen WeightOnePaulis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 8aeea795ef5409339e8a1b39c3ffcfaf29d675b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851976"
---
# <a name="weightonepaulis-function"></a>Funktionen WeightOnePaulis

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en matris med alla vikt-1 Pauli-operatorer för ett angivet antal qubits.

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a>Indata

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som de returnerade Pauli-operatörerna har definierats på.



## <a name="output--pauli"></a>Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

En matris med multi-qubit Pauli-operatorer, som var och en visas som en matris med längd `nQubits` .