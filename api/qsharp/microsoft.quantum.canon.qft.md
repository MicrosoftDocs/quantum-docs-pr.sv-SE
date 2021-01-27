---
uid: Microsoft.Quantum.Canon.QFT
title: QFT-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 30f475c3850c248b5af58db1e4aac3638c4c0471
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852302"
---
# <a name="qft-operation"></a><span data-ttu-id="3c55d-102">QFT-åtgärd</span><span class="sxs-lookup"><span data-stu-id="3c55d-102">QFT operation</span></span>

<span data-ttu-id="3c55d-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c55d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c55d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c55d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c55d-105">Utför Quantum Fourier-transformeringen på ett Quantum-register som innehåller ett heltal i big-endian-representationen.</span><span class="sxs-lookup"><span data-stu-id="3c55d-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3c55d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3c55d-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="3c55d-107">QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="3c55d-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="3c55d-108">Quantum register till vilken Quantum Fourier-transformeringen används</span><span class="sxs-lookup"><span data-stu-id="3c55d-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c55d-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c55d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3c55d-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3c55d-110">Remarks</span></span>

<span data-ttu-id="3c55d-111">Indata och utdata antas vara i big endian kodning.</span><span class="sxs-lookup"><span data-stu-id="3c55d-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c55d-112">Se även</span><span class="sxs-lookup"><span data-stu-id="3c55d-112">See Also</span></span>

- [<span data-ttu-id="3c55d-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="3c55d-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)