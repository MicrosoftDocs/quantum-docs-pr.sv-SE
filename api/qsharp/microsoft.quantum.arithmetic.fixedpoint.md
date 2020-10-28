---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: f1370cd2f8a7d6488ae0f6be841abd95e61f038e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731534"
---
# <a name="fixedpoint-user-defined-type"></a>FixedPoint-användardefinierad typ

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paketfilerna [](https://nuget.org/packages/)


Representerar ett register över qubits-kodning med ett fast punkts nummer. Består av ett heltal som är lika med antalet qubits till vänster om den binära punkten, t. ex. qubits som är större än eller lika med 1 och ett Quantum-register.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

