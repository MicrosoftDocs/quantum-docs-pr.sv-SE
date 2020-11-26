---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 65e47d82546b1df0beec2c00f435d3e7a28e6ae6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200262"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="c281b-102">SyndromeMeasOp-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="c281b-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="c281b-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c281b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c281b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c281b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c281b-105">Representerar en åtgärd som används för att mäta Syndrome för ett felkorrigerande kod block.</span><span class="sxs-lookup"><span data-stu-id="c281b-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="c281b-106">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c281b-106">Remarks</span></span>

<span data-ttu-id="c281b-107">Signaturen `(LogicalRegister => Syndrome)` representerar en åtgärd som agerar gemensamt på qubits i `LogicalRegister` och vissa hjälp qubits följt av en mätning av hjälp qubits för att extrahera ett `Syndrome` värde som representerar `Result[]` dessa mått.</span><span class="sxs-lookup"><span data-stu-id="c281b-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="c281b-108">Se även</span><span class="sxs-lookup"><span data-stu-id="c281b-108">See Also</span></span>

- [<span data-ttu-id="c281b-109">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="c281b-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="c281b-110">Microsoft. Quantum. ErrorCorrection. Syndrome</span><span class="sxs-lookup"><span data-stu-id="c281b-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)