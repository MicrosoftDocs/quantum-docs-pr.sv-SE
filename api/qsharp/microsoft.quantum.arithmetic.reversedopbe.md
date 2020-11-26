---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: Funktionen ReversedOpBE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 3c39a90ed4b5df09b90d8b5020d8b824285b50eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222328"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="37615-102">Funktionen ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="37615-102">ReversedOpBE function</span></span>

<span data-ttu-id="37615-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="37615-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="37615-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37615-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37615-105">Med en åtgärd som tar big-endian-indatamängd returnerar en ny åtgärd som tar lite-endian-indatamängd.</span><span class="sxs-lookup"><span data-stu-id="37615-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="37615-106">Indata</span><span class="sxs-lookup"><span data-stu-id="37615-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="37615-107">OP: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37615-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="37615-108">Åtgärden vars indatatyper ska ångras.</span><span class="sxs-lookup"><span data-stu-id="37615-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="37615-109">Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37615-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="37615-110">En ny åtgärd som accepterar indatatypen som ett litet endian-register.</span><span class="sxs-lookup"><span data-stu-id="37615-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="37615-111">Se även</span><span class="sxs-lookup"><span data-stu-id="37615-111">See Also</span></span>

- [<span data-ttu-id="37615-112">Microsoft. Quantum. aritmetiska. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="37615-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="37615-113">Microsoft. Quantum. aritmetiska. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="37615-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="37615-114">Microsoft. Quantum. aritmetiska. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="37615-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="37615-115">Microsoft. Quantum. aritmetiska. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="37615-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)