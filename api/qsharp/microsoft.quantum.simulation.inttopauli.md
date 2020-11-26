---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: Funktionen IntToPauli
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229213"
---
# <a name="inttopauli-function"></a>Funktionen IntToPauli

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konverterar ett heltal till en enskild-qubit Pauli-operator.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Indata

### <a name="idx--int"></a>IDX: [int](xref:microsoft.quantum.lang-ref.int)

Heltal i intervallet `0..3` som ska konverteras till Pauli-operatorer.



## <a name="output--pauli"></a>Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

En `Pauli` operator som angetts av `[PauliI, PauliX, PauliY, PauliZ][idx]` .