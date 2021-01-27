---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: Funktionen IntToPauli
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 76f482b86ff4a27b6e6ce6ae4ec3d59422563f12
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842257"
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