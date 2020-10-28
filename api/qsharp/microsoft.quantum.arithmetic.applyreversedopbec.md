---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC
title: ApplyReversedOpBEC-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEC
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 54c35ccea5e9c2d3ec7a3e6f325f78c3e602970e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731755"
---
# <a name="applyreversedopbec-operation"></a><span data-ttu-id="145c3-102">ApplyReversedOpBEC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="145c3-102">ApplyReversedOpBEC operation</span></span>

<span data-ttu-id="145c3-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="145c3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="145c3-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="145c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="145c3-105">Tillämpar en åtgärd som tar big-endian-inläsningar till ett register som kodar ett osignerat heltal med litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="145c3-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="145c3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="145c3-106">Input</span></span>

### <a name="op--bigendian--unit-ctl"></a><span data-ttu-id="145c3-107">OP: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [enhet](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="145c3-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="145c3-108">Åtgärd som agerar på ett big-endian-register.</span><span class="sxs-lookup"><span data-stu-id="145c3-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="145c3-109">Registrera: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="145c3-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="145c3-110">Ett litet endian-register som ska omvandlas.</span><span class="sxs-lookup"><span data-stu-id="145c3-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="145c3-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="145c3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="145c3-112">Se även</span><span class="sxs-lookup"><span data-stu-id="145c3-112">See Also</span></span>

- [<span data-ttu-id="145c3-113">Microsoft. Quantum. aritmetiska. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="145c3-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="145c3-114">Microsoft. Quantum. aritmetiska. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="145c3-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="145c3-115">Microsoft. Quantum. aritmetiska. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="145c3-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)