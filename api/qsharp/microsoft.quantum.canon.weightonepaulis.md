---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: Funktionen WeightOnePaulis
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 904c606393131d51eaa44d464ad52bec509eaf72
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204546"
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