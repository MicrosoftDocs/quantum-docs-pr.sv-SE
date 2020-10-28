---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: Funktionen IntsToPaulis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725821"
---
# <a name="intstopaulis-function"></a>Funktionen IntsToPaulis

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paketfilerna [](https://nuget.org/packages/)


Konverterar en matris med heltal till en matris med en qubit Pauli-operator.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Indata

### <a name="ints--int"></a>InTS: [int](xref:microsoft.quantum.lang-ref.int)[]

Matris med heltal i intervallet som ska `0..3`  konverteras till Pauli-operatorer.



## <a name="output--pauli"></a>Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

En matris `paulis` med Pauli-operatorer `Pauli[]` har samma längd som det som `ints` `paulis[idxPauli]` är lika med det element som `[PauliI, PauliX, PauliY, PauliZ]` anges av `ints[idxPauli]` .