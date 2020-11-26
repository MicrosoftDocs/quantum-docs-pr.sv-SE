---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 39a2dc2fe33f46c2767def06a44cde07e2f01497
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223297"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="85489-102">CopyMostSignificantBit-åtgärd</span><span class="sxs-lookup"><span data-stu-id="85489-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="85489-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="85489-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="85489-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85489-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85489-105">Kopierar den mest signifikanta biten i ett qubit-register `from` som representerar ett osignerat heltal till qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="85489-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="85489-106">Indata</span><span class="sxs-lookup"><span data-stu-id="85489-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="85489-107">från: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="85489-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="85489-108">Det osignerade heltalet som den högsta biten kopieras från.</span><span class="sxs-lookup"><span data-stu-id="85489-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="85489-109">heltalet är kodat i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="85489-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="85489-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="85489-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="85489-111">Qubit som den högsta biten kopieras till.</span><span class="sxs-lookup"><span data-stu-id="85489-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="85489-112">Bit kodningen används i beräknings basen.</span><span class="sxs-lookup"><span data-stu-id="85489-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="85489-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="85489-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="85489-114">Se även</span><span class="sxs-lookup"><span data-stu-id="85489-114">See Also</span></span>

- [<span data-ttu-id="85489-115">Microsoft. Quantum. aritmetiska. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="85489-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)