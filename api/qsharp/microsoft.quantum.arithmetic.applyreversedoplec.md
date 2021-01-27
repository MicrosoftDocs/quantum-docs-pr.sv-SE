---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: ApplyReversedOpLEC-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 74ecc705a6e3d1d59c4c4ae71d30171c12fa45ae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843506"
---
# <a name="applyreversedoplec-operation"></a><span data-ttu-id="05a29-102">ApplyReversedOpLEC-åtgärd</span><span class="sxs-lookup"><span data-stu-id="05a29-102">ApplyReversedOpLEC operation</span></span>

<span data-ttu-id="05a29-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="05a29-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="05a29-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="05a29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="05a29-105">Använder en åtgärd som tar lite-endian-inmatad till en register kodning av ett osignerat heltal med big-endian-format.</span><span class="sxs-lookup"><span data-stu-id="05a29-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="05a29-106">Indata</span><span class="sxs-lookup"><span data-stu-id="05a29-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="05a29-107">OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="05a29-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="05a29-108">Åtgärd som agerar på ett litet-endian-register.</span><span class="sxs-lookup"><span data-stu-id="05a29-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="05a29-109">Registrera: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="05a29-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="05a29-110">Ett big-endian-register som ska omvandlas.</span><span class="sxs-lookup"><span data-stu-id="05a29-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05a29-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05a29-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="05a29-112">Se även</span><span class="sxs-lookup"><span data-stu-id="05a29-112">See Also</span></span>

- [<span data-ttu-id="05a29-113">Microsoft. Quantum. aritmetiska. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="05a29-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="05a29-114">Microsoft. Quantum. aritmetiska. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="05a29-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="05a29-115">Microsoft. Quantum. aritmetiska. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="05a29-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)