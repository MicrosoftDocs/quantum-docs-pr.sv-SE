---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: ApplyQuantumFourierTransformBE-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 39db7b4c69f7f06418ec257c013837c65b9cc67a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209051"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="6b4ed-102">ApplyQuantumFourierTransformBE-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6b4ed-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="6b4ed-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6b4ed-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6b4ed-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b4ed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b4ed-105">Utför Quantum Fourier-transformeringen på ett Quantum-register som innehåller ett heltal i big-endian-representationen.</span><span class="sxs-lookup"><span data-stu-id="6b4ed-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6b4ed-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6b4ed-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="6b4ed-107">QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="6b4ed-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="6b4ed-108">Quantum register till vilken Quantum Fourier-transformeringen används</span><span class="sxs-lookup"><span data-stu-id="6b4ed-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b4ed-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b4ed-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6b4ed-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6b4ed-110">Remarks</span></span>

<span data-ttu-id="6b4ed-111">Indata och utdata antas vara i big endian kodning.</span><span class="sxs-lookup"><span data-stu-id="6b4ed-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b4ed-112">Se även</span><span class="sxs-lookup"><span data-stu-id="6b4ed-112">See Also</span></span>

- [<span data-ttu-id="6b4ed-113">Microsoft. Quantum. Canon. ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="6b4ed-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="6b4ed-114">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="6b4ed-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)