---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC
title: ApplyReversedOpBEC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEC
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 7d118d1b04c37a80e61dfab2ee2265b3596b5877
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843564"
---
# <a name="applyreversedopbec-operation"></a><span data-ttu-id="c288a-102">ApplyReversedOpBEC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c288a-102">ApplyReversedOpBEC operation</span></span>

<span data-ttu-id="c288a-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c288a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c288a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c288a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c288a-105">Tillämpar en åtgärd som tar big-endian-inläsningar till ett register som kodar ett osignerat heltal med litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="c288a-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="c288a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c288a-106">Input</span></span>

### <a name="op--bigendian--unit--is-ctl"></a><span data-ttu-id="c288a-107">OP: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="c288a-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c288a-108">Åtgärd som agerar på ett big-endian-register.</span><span class="sxs-lookup"><span data-stu-id="c288a-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="c288a-109">Registrera: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c288a-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c288a-110">Ett litet endian-register som ska omvandlas.</span><span class="sxs-lookup"><span data-stu-id="c288a-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c288a-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c288a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c288a-112">Se även</span><span class="sxs-lookup"><span data-stu-id="c288a-112">See Also</span></span>

- [<span data-ttu-id="c288a-113">Microsoft. Quantum. aritmetiska. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="c288a-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="c288a-114">Microsoft. Quantum. aritmetiska. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="c288a-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="c288a-115">Microsoft. Quantum. aritmetiska. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="c288a-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)