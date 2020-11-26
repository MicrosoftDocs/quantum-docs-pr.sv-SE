---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: Funktionen ReversedOpLE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 91b98663028b8a1d54c546e70d8bfe603d71d041
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222260"
---
# <a name="reversedople-function"></a><span data-ttu-id="fe432-102">Funktionen ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="fe432-102">ReversedOpLE function</span></span>

<span data-ttu-id="fe432-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fe432-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fe432-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe432-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe432-105">Med en åtgärd som tar lite-endian-indatamängd returnerar en ny åtgärd som tar en big-endian-indatamängd.</span><span class="sxs-lookup"><span data-stu-id="fe432-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="fe432-106">Indata</span><span class="sxs-lookup"><span data-stu-id="fe432-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="fe432-107">OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe432-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fe432-108">Åtgärden vars indatatyper ska ångras.</span><span class="sxs-lookup"><span data-stu-id="fe432-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="fe432-109">Utdata: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe432-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fe432-110">En ny åtgärd som accepterar indatatypen som en big-endian-registrering.</span><span class="sxs-lookup"><span data-stu-id="fe432-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe432-111">Se även</span><span class="sxs-lookup"><span data-stu-id="fe432-111">See Also</span></span>

- [<span data-ttu-id="fe432-112">Microsoft. Quantum. aritmetiska. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="fe432-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="fe432-113">Microsoft. Quantum. aritmetiska. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="fe432-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="fe432-114">Microsoft. Quantum. aritmetiska. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="fe432-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="fe432-115">Microsoft. Quantum. aritmetiska. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="fe432-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)