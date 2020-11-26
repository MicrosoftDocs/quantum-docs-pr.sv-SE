---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: Funktionen ReversedOpLEA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 71b6b87a44f541e5379d8de8a3562febbfa49e1d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222175"
---
# <a name="reversedoplea-function"></a><span data-ttu-id="49d6e-102">Funktionen ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="49d6e-102">ReversedOpLEA function</span></span>

<span data-ttu-id="49d6e-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="49d6e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="49d6e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="49d6e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="49d6e-105">Med en åtgärd som tar lite-endian-indatamängd returnerar en ny åtgärd som tar en big-endian-indatamängd.</span><span class="sxs-lookup"><span data-stu-id="49d6e-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="49d6e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="49d6e-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="49d6e-107">OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejust</span><span class="sxs-lookup"><span data-stu-id="49d6e-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="49d6e-108">Åtgärden vars indatatyper ska ångras.</span><span class="sxs-lookup"><span data-stu-id="49d6e-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-adj"></a><span data-ttu-id="49d6e-109">Utdata: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejust</span><span class="sxs-lookup"><span data-stu-id="49d6e-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="49d6e-110">En ny åtgärd som accepterar indatatypen som en big-endian-registrering.</span><span class="sxs-lookup"><span data-stu-id="49d6e-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="49d6e-111">Se även</span><span class="sxs-lookup"><span data-stu-id="49d6e-111">See Also</span></span>

- [<span data-ttu-id="49d6e-112">Microsoft. Quantum. aritmetiska. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="49d6e-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="49d6e-113">Microsoft. Quantum. aritmetiska. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="49d6e-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="49d6e-114">Microsoft. Quantum. aritmetiska. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="49d6e-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="49d6e-115">Microsoft. Quantum. aritmetiska. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="49d6e-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)