---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA
title: ApplyReversedOpLEA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 572841410f16085256fdee9302038cd347476dd9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843516"
---
# <a name="applyreversedoplea-operation"></a><span data-ttu-id="fddff-102">ApplyReversedOpLEA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="fddff-102">ApplyReversedOpLEA operation</span></span>

<span data-ttu-id="fddff-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fddff-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fddff-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fddff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fddff-105">Använder en åtgärd som tar lite-endian-inmatad till en register kodning av ett osignerat heltal med big-endian-format.</span><span class="sxs-lookup"><span data-stu-id="fddff-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="fddff-106">Indata</span><span class="sxs-lookup"><span data-stu-id="fddff-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="fddff-107">OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejust</span><span class="sxs-lookup"><span data-stu-id="fddff-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="fddff-108">Åtgärd som agerar på ett litet-endian-register.</span><span class="sxs-lookup"><span data-stu-id="fddff-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="fddff-109">Registrera: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="fddff-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="fddff-110">Ett big-endian-register som ska omvandlas.</span><span class="sxs-lookup"><span data-stu-id="fddff-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fddff-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fddff-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="fddff-112">Se även</span><span class="sxs-lookup"><span data-stu-id="fddff-112">See Also</span></span>

- [<span data-ttu-id="fddff-113">Microsoft. Quantum. aritmetiska. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="fddff-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="fddff-114">Microsoft. Quantum. aritmetiska. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="fddff-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="fddff-115">Microsoft. Quantum. aritmetiska. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="fddff-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)