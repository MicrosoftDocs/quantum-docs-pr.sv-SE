---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBECA
title: Funktionen ReversedOpBECA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBECA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: da21b09110400ad4ee862f662d45e166a49e7bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222209"
---
# <a name="reversedopbeca-function"></a><span data-ttu-id="b2c8d-102">Funktionen ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="b2c8d-102">ReversedOpBECA function</span></span>

<span data-ttu-id="b2c8d-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b2c8d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b2c8d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2c8d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2c8d-105">Med en åtgärd som tar big-endian-indatamängd returnerar en ny åtgärd som tar lite-endian-indatamängd.</span><span class="sxs-lookup"><span data-stu-id="b2c8d-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="b2c8d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b2c8d-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="b2c8d-107">OP: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejusts + CTL</span><span class="sxs-lookup"><span data-stu-id="b2c8d-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b2c8d-108">Åtgärden vars indatatyper ska ångras.</span><span class="sxs-lookup"><span data-stu-id="b2c8d-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="b2c8d-109">Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejusts + CTL</span><span class="sxs-lookup"><span data-stu-id="b2c8d-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b2c8d-110">En ny åtgärd som accepterar indatatypen som ett litet endian-register.</span><span class="sxs-lookup"><span data-stu-id="b2c8d-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2c8d-111">Se även</span><span class="sxs-lookup"><span data-stu-id="b2c8d-111">See Also</span></span>

- [<span data-ttu-id="b2c8d-112">Microsoft. Quantum. aritmetiska. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="b2c8d-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
- [<span data-ttu-id="b2c8d-113">Microsoft. Quantum. aritmetiska. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="b2c8d-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="b2c8d-114">Microsoft. Quantum. aritmetiska. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="b2c8d-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="b2c8d-115">Microsoft. Quantum. aritmetiska. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="b2c8d-115">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)