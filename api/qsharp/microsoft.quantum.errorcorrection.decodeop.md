---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: DecodeOp-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: f1fc2851b7ed8b12cf8a47fabe794235a3083d31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201010"
---
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="a2f10-102">DecodeOp-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="a2f10-102">DecodeOp user defined type</span></span>

<span data-ttu-id="a2f10-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a2f10-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a2f10-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2f10-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2f10-105">Representerar en åtgärd som avkodar en kodad register till ett fysiskt register och den Scratch-qubits som används för att registrera en syndrome.</span><span class="sxs-lookup"><span data-stu-id="a2f10-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="a2f10-106">Argumentet till en DecodeOp är detsamma som returvärdet från en EncodeOp och vice versa.</span><span class="sxs-lookup"><span data-stu-id="a2f10-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

