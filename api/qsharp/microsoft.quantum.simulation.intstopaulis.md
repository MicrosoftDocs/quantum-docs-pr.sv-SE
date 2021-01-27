---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: Funktionen IntsToPaulis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 6904054bb1aff3a57c80882694b4c217812b2b81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842228"
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