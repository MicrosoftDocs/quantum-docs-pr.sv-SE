---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: EncodeOp-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: da947cdc25cb0edd3a4144022bbfc6ecb84c647f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727063"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="875f1-102">EncodeOp-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="875f1-102">EncodeOp user defined type</span></span>

<span data-ttu-id="875f1-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="875f1-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="875f1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="875f1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="875f1-105">Representerar en åtgärd som kodar ett fysiskt register i ett logiskt register med hjälp av det tillhandahållna qubits.</span><span class="sxs-lookup"><span data-stu-id="875f1-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="875f1-106">Det första argumentet är att vara det fysiska register som kommer att kodas, medan det andra argumentet tas som det första registret som ska användas.</span><span class="sxs-lookup"><span data-stu-id="875f1-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

