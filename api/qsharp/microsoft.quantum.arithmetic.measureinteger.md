---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: e3ff06e5cbb2ef8a63e4ad12308b382347c90fc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222651"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="a9d2d-102">MeasureInteger-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a9d2d-102">MeasureInteger operation</span></span>

<span data-ttu-id="a9d2d-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a9d2d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a9d2d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a9d2d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a9d2d-105">Mäter innehållet i ett Quantum-register och konverterar det till ett heltal.</span><span class="sxs-lookup"><span data-stu-id="a9d2d-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="a9d2d-106">Mätningen utförs med avseende på standard beräknings basen, d.v.s. eigenbasis `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="a9d2d-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="a9d2d-107">Indata</span><span class="sxs-lookup"><span data-stu-id="a9d2d-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="a9d2d-108">mål: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a9d2d-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a9d2d-109">Ett Quantum-register i den lilla endian-kodningen.</span><span class="sxs-lookup"><span data-stu-id="a9d2d-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="a9d2d-110">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a9d2d-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a9d2d-111">Ett osignerat heltal som innehåller det uppmätta värdet `target` .</span><span class="sxs-lookup"><span data-stu-id="a9d2d-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a9d2d-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a9d2d-112">Remarks</span></span>

<span data-ttu-id="a9d2d-113">Den här åtgärden återställer ingångs register till $ \ket{00\cdots 0} $ State, vilket är lämpligt för att frigöra tillbaka till en måldator.</span><span class="sxs-lookup"><span data-stu-id="a9d2d-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9d2d-114">Se även</span><span class="sxs-lookup"><span data-stu-id="a9d2d-114">See Also</span></span>

- [<span data-ttu-id="a9d2d-115">Microsoft. Quantum. Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="a9d2d-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)