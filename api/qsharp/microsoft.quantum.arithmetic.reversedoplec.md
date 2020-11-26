---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: Funktionen ReversedOpLEC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 8c91391691b23786df02ae2a35264b578dccad41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222090"
---
# <a name="reversedoplec-function"></a><span data-ttu-id="6d546-102">Funktionen ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="6d546-102">ReversedOpLEC function</span></span>

<span data-ttu-id="6d546-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6d546-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6d546-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6d546-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6d546-105">Med en åtgärd som tar lite-endian-indatamängd returnerar en ny åtgärd som tar en big-endian-indatamängd.</span><span class="sxs-lookup"><span data-stu-id="6d546-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="6d546-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6d546-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="6d546-107">OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="6d546-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="6d546-108">Åtgärden vars indatatyper ska ångras.</span><span class="sxs-lookup"><span data-stu-id="6d546-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-ctl"></a><span data-ttu-id="6d546-109">Utdata: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  är CTL</span><span class="sxs-lookup"><span data-stu-id="6d546-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="6d546-110">En ny åtgärd som accepterar indatatypen som en big-endian-registrering.</span><span class="sxs-lookup"><span data-stu-id="6d546-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d546-111">Se även</span><span class="sxs-lookup"><span data-stu-id="6d546-111">See Also</span></span>

- [<span data-ttu-id="6d546-112">Microsoft. Quantum. aritmetiska. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="6d546-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="6d546-113">Microsoft. Quantum. aritmetiska. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="6d546-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="6d546-114">Microsoft. Quantum. aritmetiska. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="6d546-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="6d546-115">Microsoft. Quantum. aritmetiska. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="6d546-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)