---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 59df1db31090f875ccd261fe6cc43995ba57b963
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842989"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="039e6-102">PhaseLittleEndian-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="039e6-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="039e6-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="039e6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="039e6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="039e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="039e6-105">Små endian-osignerade heltal i QFT-basen.</span><span class="sxs-lookup"><span data-stu-id="039e6-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="039e6-106">Om t. ex. $ \ket{x} $ är den lilla endian-kodningen av heltals-$x $ i beräknings basen, är $ \operatorname{QFTLE} \ket{x} $ kodningen för $x $ i QFT-basen.</span><span class="sxs-lookup"><span data-stu-id="039e6-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="039e6-107">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="039e6-107">Remarks</span></span>

<span data-ttu-id="039e6-108">Vi förkortar `PhaseLittleEndian` som `PhaseLE` i dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="039e6-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="039e6-109">Se även</span><span class="sxs-lookup"><span data-stu-id="039e6-109">See Also</span></span>

- [<span data-ttu-id="039e6-110">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="039e6-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="039e6-111">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="039e6-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)