---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843109"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="84e64-102">MeasureInteger-åtgärd</span><span class="sxs-lookup"><span data-stu-id="84e64-102">MeasureInteger operation</span></span>

<span data-ttu-id="84e64-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="84e64-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="84e64-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84e64-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84e64-105">Mäter innehållet i ett Quantum-register och konverterar det till ett heltal.</span><span class="sxs-lookup"><span data-stu-id="84e64-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="84e64-106">Mätningen utförs med avseende på standard beräknings basen, d.v.s. eigenbasis `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="84e64-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="84e64-107">Indata</span><span class="sxs-lookup"><span data-stu-id="84e64-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="84e64-108">mål: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="84e64-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="84e64-109">Ett Quantum-register i den lilla endian-kodningen.</span><span class="sxs-lookup"><span data-stu-id="84e64-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="84e64-110">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="84e64-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="84e64-111">Ett osignerat heltal som innehåller det uppmätta värdet `target` .</span><span class="sxs-lookup"><span data-stu-id="84e64-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="84e64-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="84e64-112">Remarks</span></span>

<span data-ttu-id="84e64-113">Den här åtgärden återställer ingångs register till $ \ket{00\cdots 0} $ State, vilket är lämpligt för att frigöra tillbaka till en måldator.</span><span class="sxs-lookup"><span data-stu-id="84e64-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="84e64-114">Se även</span><span class="sxs-lookup"><span data-stu-id="84e64-114">See Also</span></span>

- [<span data-ttu-id="84e64-115">Microsoft. Quantum. Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="84e64-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)