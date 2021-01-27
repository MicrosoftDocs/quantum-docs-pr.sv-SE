---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 609e937a03bebf45aa9398225bd1b7e2b717807a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843274"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="bd0ee-102">CopyMostSignificantBit-åtgärd</span><span class="sxs-lookup"><span data-stu-id="bd0ee-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="bd0ee-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bd0ee-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bd0ee-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd0ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd0ee-105">Kopierar den mest signifikanta biten i ett qubit-register `from` som representerar ett osignerat heltal till qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="bd0ee-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="bd0ee-106">Indata</span><span class="sxs-lookup"><span data-stu-id="bd0ee-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="bd0ee-107">från: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bd0ee-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bd0ee-108">Det osignerade heltalet som den högsta biten kopieras från.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="bd0ee-109">heltalet är kodat i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="bd0ee-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bd0ee-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bd0ee-111">Qubit som den högsta biten kopieras till.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="bd0ee-112">Bit kodningen används i beräknings basen.</span><span class="sxs-lookup"><span data-stu-id="bd0ee-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd0ee-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd0ee-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="bd0ee-114">Se även</span><span class="sxs-lookup"><span data-stu-id="bd0ee-114">See Also</span></span>

- [<span data-ttu-id="bd0ee-115">Microsoft. Quantum. aritmetiska. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="bd0ee-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)