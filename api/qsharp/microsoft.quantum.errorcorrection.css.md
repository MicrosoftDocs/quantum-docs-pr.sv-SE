---
uid: Microsoft.Quantum.ErrorCorrection.CSS
title: CSS-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: CSS
qsharp.summary: Represents a Calderbank–Shor–Steane (CSS) code as defined by its encoder, decoder, and its syndrome measurement procedures for `X` and `Z` errors, respectively.
ms.openlocfilehash: f02412f065991a6717514a87c9afea177c8d3444
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201180"
---
# <a name="css-user-defined-type"></a><span data-ttu-id="7909a-102">CSS-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="7909a-102">CSS user defined type</span></span>

<span data-ttu-id="7909a-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7909a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7909a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7909a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7909a-105">Representerar en kod för Calderbank – Shor – Steane (CSS) som definieras av dess kodare, avkodare och dess Syndrome mått procedurer för `X` `Z` respektive fel.</span><span class="sxs-lookup"><span data-stu-id="7909a-105">Represents a Calderbank–Shor–Steane (CSS) code as defined by its encoder, decoder, and its syndrome measurement procedures for `X` and `Z` errors, respectively.</span></span>

```qsharp

newtype CSS = (Microsoft.Quantum.ErrorCorrection.EncodeOp, Microsoft.Quantum.ErrorCorrection.DecodeOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp);
```

