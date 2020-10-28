---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730590"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="59f91-102">PhaseLittleEndian-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="59f91-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="59f91-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="59f91-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="59f91-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="59f91-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="59f91-105">Små endian-osignerade heltal i QFT-basen.</span><span class="sxs-lookup"><span data-stu-id="59f91-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="59f91-106">Om t. ex. $ \ket{x} $ är den lilla endian-kodningen av heltals-$x $ i beräknings basen, är $ \operatorname{QFTLE} \ket{x} $ kodningen för $x $ i QFT-basen.</span><span class="sxs-lookup"><span data-stu-id="59f91-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="59f91-107">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="59f91-107">Remarks</span></span>

<span data-ttu-id="59f91-108">Vi förkortar `PhaseLittleEndian` som `PhaseLE` i dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="59f91-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="59f91-109">Se även</span><span class="sxs-lookup"><span data-stu-id="59f91-109">See Also</span></span>

- [<span data-ttu-id="59f91-110">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="59f91-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="59f91-111">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="59f91-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)