---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: Funktionen ReversedOpBEC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5bafe71b665eda082eafbe06be1308d6b042db2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222277"
---
# <a name="reversedopbec-function"></a><span data-ttu-id="d48de-102">Funktionen ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="d48de-102">ReversedOpBEC function</span></span>

<span data-ttu-id="d48de-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d48de-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d48de-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d48de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d48de-105">Med en åtgärd som tar big-endian-indatamängd returnerar en ny åtgärd som tar lite-endian-indatamängd.</span><span class="sxs-lookup"><span data-stu-id="d48de-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="d48de-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d48de-106">Input</span></span>

### <a name="op--bigendian--unit--is-ctl"></a><span data-ttu-id="d48de-107">OP: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="d48de-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d48de-108">Åtgärden vars indatatyper ska ångras.</span><span class="sxs-lookup"><span data-stu-id="d48de-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-ctl"></a><span data-ttu-id="d48de-109">Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="d48de-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d48de-110">En ny åtgärd som accepterar indatatypen som ett litet endian-register.</span><span class="sxs-lookup"><span data-stu-id="d48de-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="d48de-111">Se även</span><span class="sxs-lookup"><span data-stu-id="d48de-111">See Also</span></span>

- [<span data-ttu-id="d48de-112">Microsoft. Quantum. aritmetiska. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="d48de-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="d48de-113">Microsoft. Quantum. aritmetiska. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="d48de-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="d48de-114">Microsoft. Quantum. aritmetiska. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="d48de-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="d48de-115">Microsoft. Quantum. aritmetiska. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="d48de-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)