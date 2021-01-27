---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBE
title: ApplyReversedOpBE-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBE
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: bf2d43d4e870150f8e6d51dc2f5fb37bdf01d6ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843616"
---
# <a name="applyreversedopbe-operation"></a><span data-ttu-id="90b4a-102">ApplyReversedOpBE-åtgärd</span><span class="sxs-lookup"><span data-stu-id="90b4a-102">ApplyReversedOpBE operation</span></span>

<span data-ttu-id="90b4a-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="90b4a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="90b4a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90b4a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90b4a-105">Tillämpar en åtgärd som tar big-endian-inläsningar till ett register som kodar ett osignerat heltal med litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="90b4a-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="90b4a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="90b4a-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="90b4a-107">OP: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90b4a-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="90b4a-108">Åtgärd som agerar på ett big-endian-register.</span><span class="sxs-lookup"><span data-stu-id="90b4a-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="90b4a-109">Registrera: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="90b4a-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="90b4a-110">Ett litet endian-register som ska omvandlas.</span><span class="sxs-lookup"><span data-stu-id="90b4a-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="90b4a-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90b4a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="90b4a-112">Se även</span><span class="sxs-lookup"><span data-stu-id="90b4a-112">See Also</span></span>

- [<span data-ttu-id="90b4a-113">Microsoft. Quantum. aritmetiska. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="90b4a-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="90b4a-114">Microsoft. Quantum. aritmetiska. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="90b4a-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="90b4a-115">Microsoft. Quantum. aritmetiska. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="90b4a-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)