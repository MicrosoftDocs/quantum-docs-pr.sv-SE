---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 18e85120647c5a1f41ccab5fbfb27ea602a279af
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843208"
---
# <a name="fixedpoint-user-defined-type"></a>FixedPoint-användardefinierad typ

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Representerar ett register över qubits-kodning med ett fast punkts nummer. Består av ett heltal som är lika med antalet qubits till vänster om den binära punkten, t. ex. qubits som är större än eller lika med 1 och ett Quantum-register.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

