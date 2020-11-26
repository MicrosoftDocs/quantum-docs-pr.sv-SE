---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: Funktionen IntsToPaulis
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 2333dcbd2988480e2b2b9b217b26705f3578de00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230539"
---
# <a name="intstopaulis-function"></a>Funktionen IntsToPaulis

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konverterar en matris med heltal till en matris med en qubit Pauli-operator.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Indata

### <a name="ints--int"></a>InTS: [int](xref:microsoft.quantum.lang-ref.int)[]

Matris med heltal i intervallet som ska `0..3`  konverteras till Pauli-operatorer.



## <a name="output--pauli"></a>Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

En matris `paulis` med Pauli-operatorer `Pauli[]` har samma längd som det som `ints` `paulis[idxPauli]` är lika med det element som `[PauliI, PauliX, PauliY, PauliZ]` anges av `ints[idxPauli]` .