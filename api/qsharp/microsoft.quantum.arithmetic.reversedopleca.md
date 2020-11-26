---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: Funktionen ReversedOpLECA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: c058243db2b4cee3a72e025b084b4f98f7020a6b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222073"
---
# <a name="reversedopleca-function"></a><span data-ttu-id="f8292-102">Funktionen ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="f8292-102">ReversedOpLECA function</span></span>

<span data-ttu-id="f8292-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f8292-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f8292-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f8292-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f8292-105">Med en åtgärd som tar lite-endian-indatamängd returnerar en ny åtgärd som tar en big-endian-indatamängd.</span><span class="sxs-lookup"><span data-stu-id="f8292-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="f8292-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f8292-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="f8292-107">OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejusts + CTL</span><span class="sxs-lookup"><span data-stu-id="f8292-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f8292-108">Åtgärden vars indatatyper ska ångras.</span><span class="sxs-lookup"><span data-stu-id="f8292-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="f8292-109">Utdata: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejusts + CTL</span><span class="sxs-lookup"><span data-stu-id="f8292-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f8292-110">En ny åtgärd som accepterar indatatypen som en big-endian-registrering.</span><span class="sxs-lookup"><span data-stu-id="f8292-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8292-111">Se även</span><span class="sxs-lookup"><span data-stu-id="f8292-111">See Also</span></span>

- [<span data-ttu-id="f8292-112">Microsoft. Quantum. aritmetiska. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="f8292-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [<span data-ttu-id="f8292-113">Microsoft. Quantum. aritmetiska. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="f8292-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="f8292-114">Microsoft. Quantum. aritmetiska. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="f8292-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="f8292-115">Microsoft. Quantum. aritmetiska. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="f8292-115">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)