---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: Funktionen ReversedOpBEA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 69fd4401e6862a3a6afaa51fb5b8a3592768bb42
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222311"
---
# <a name="reversedopbea-function"></a><span data-ttu-id="af37d-102">Funktionen ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="af37d-102">ReversedOpBEA function</span></span>

<span data-ttu-id="af37d-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="af37d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="af37d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="af37d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="af37d-105">Med en åtgärd som tar big-endian-indatamängd returnerar en ny åtgärd som tar lite-endian-indatamängd.</span><span class="sxs-lookup"><span data-stu-id="af37d-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="af37d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="af37d-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj"></a><span data-ttu-id="af37d-107">OP: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejust</span><span class="sxs-lookup"><span data-stu-id="af37d-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="af37d-108">Åtgärden vars indatatyper ska ångras.</span><span class="sxs-lookup"><span data-stu-id="af37d-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-adj"></a><span data-ttu-id="af37d-109">Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejust</span><span class="sxs-lookup"><span data-stu-id="af37d-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="af37d-110">En ny åtgärd som accepterar indatatypen som ett litet endian-register.</span><span class="sxs-lookup"><span data-stu-id="af37d-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="af37d-111">Se även</span><span class="sxs-lookup"><span data-stu-id="af37d-111">See Also</span></span>

- [<span data-ttu-id="af37d-112">Microsoft. Quantum. aritmetiska. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="af37d-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="af37d-113">Microsoft. Quantum. aritmetiska. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="af37d-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="af37d-114">Microsoft. Quantum. aritmetiska. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="af37d-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="af37d-115">Microsoft. Quantum. aritmetiska. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="af37d-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)