---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 0fea6e4ee1b8c5391e815217f1ddf9e511d46463
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223110"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="d2732-102">FixedPoint-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="d2732-102">FixedPoint user defined type</span></span>

<span data-ttu-id="d2732-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d2732-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d2732-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="d2732-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="d2732-105">Representerar ett register över qubits-kodning med ett fast punkts nummer.</span><span class="sxs-lookup"><span data-stu-id="d2732-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="d2732-106">Består av ett heltal som är lika med antalet qubits till vänster om den binära punkten, t. ex. qubits som är större än eller lika med 1 och ett Quantum-register.</span><span class="sxs-lookup"><span data-stu-id="d2732-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

