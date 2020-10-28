---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: Funktionen IntToPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733702"
---
# <a name="inttopauli-function"></a>Funktionen IntToPauli

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paketfilerna [](https://nuget.org/packages/)


Konverterar ett heltal till en enskild-qubit Pauli-operator.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Indata

### <a name="idx--int"></a>IDX: [int](xref:microsoft.quantum.lang-ref.int)

Heltal i intervallet `0..3` som ska konverteras till Pauli-operatorer.



## <a name="output--pauli"></a>Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

En `Pauli` operator som angetts av `[PauliI, PauliX, PauliY, PauliZ][idx]` .