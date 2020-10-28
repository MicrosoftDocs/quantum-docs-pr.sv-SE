---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731579"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="39de7-102">CopyMostSignificantBit-åtgärd</span><span class="sxs-lookup"><span data-stu-id="39de7-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="39de7-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="39de7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="39de7-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39de7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39de7-105">Kopierar den mest signifikanta biten i ett qubit-register `from` som representerar ett osignerat heltal till qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="39de7-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="39de7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="39de7-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="39de7-107">från: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="39de7-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="39de7-108">Det osignerade heltalet som den högsta biten kopieras från.</span><span class="sxs-lookup"><span data-stu-id="39de7-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="39de7-109">heltalet är kodat i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="39de7-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="39de7-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="39de7-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="39de7-111">Qubit som den högsta biten kopieras till.</span><span class="sxs-lookup"><span data-stu-id="39de7-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="39de7-112">Bit kodningen används i beräknings basen.</span><span class="sxs-lookup"><span data-stu-id="39de7-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39de7-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39de7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="39de7-114">Se även</span><span class="sxs-lookup"><span data-stu-id="39de7-114">See Also</span></span>

- [<span data-ttu-id="39de7-115">Microsoft. Quantum. aritmetiska. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="39de7-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)