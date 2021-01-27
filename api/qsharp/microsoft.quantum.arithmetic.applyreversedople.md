---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLE
title: ApplyReversedOpLE-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLE
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 5f26a25afe5e3d52bae7f7c1b9c8146e5f8a747c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843548"
---
# <a name="applyreversedople-operation"></a><span data-ttu-id="20c8c-102">ApplyReversedOpLE-åtgärd</span><span class="sxs-lookup"><span data-stu-id="20c8c-102">ApplyReversedOpLE operation</span></span>

<span data-ttu-id="20c8c-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="20c8c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="20c8c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="20c8c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="20c8c-105">Använder en åtgärd som tar lite-endian-inmatad till en register kodning av ett osignerat heltal med big-endian-format.</span><span class="sxs-lookup"><span data-stu-id="20c8c-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="20c8c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="20c8c-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="20c8c-107">OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20c8c-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="20c8c-108">Åtgärd som agerar på ett litet-endian-register.</span><span class="sxs-lookup"><span data-stu-id="20c8c-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="20c8c-109">Registrera: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="20c8c-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="20c8c-110">Ett big-endian-register som ska omvandlas.</span><span class="sxs-lookup"><span data-stu-id="20c8c-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="20c8c-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20c8c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="20c8c-112">Se även</span><span class="sxs-lookup"><span data-stu-id="20c8c-112">See Also</span></span>

- [<span data-ttu-id="20c8c-113">Microsoft. Quantum. aritmetiska. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="20c8c-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="20c8c-114">Microsoft. Quantum. aritmetiska. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="20c8c-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="20c8c-115">Microsoft. Quantum. aritmetiska. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="20c8c-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)