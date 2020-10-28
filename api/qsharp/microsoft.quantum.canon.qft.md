---
uid: Microsoft.Quantum.Canon.QFT
title: QFT-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: e5b40be6c86647205fe1c764b6b043272296a354
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728479"
---
# <a name="qft-operation"></a><span data-ttu-id="4851c-102">QFT-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4851c-102">QFT operation</span></span>

<span data-ttu-id="4851c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4851c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4851c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4851c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4851c-105">Utför Quantum Fourier-transformeringen på ett Quantum-register som innehåller ett heltal i big-endian-representationen.</span><span class="sxs-lookup"><span data-stu-id="4851c-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="4851c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4851c-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="4851c-107">QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="4851c-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="4851c-108">Quantum register till vilken Quantum Fourier-transformeringen används</span><span class="sxs-lookup"><span data-stu-id="4851c-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="4851c-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4851c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4851c-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4851c-110">Remarks</span></span>

<span data-ttu-id="4851c-111">Indata och utdata antas vara i big endian kodning.</span><span class="sxs-lookup"><span data-stu-id="4851c-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="4851c-112">Se även</span><span class="sxs-lookup"><span data-stu-id="4851c-112">See Also</span></span>

- [<span data-ttu-id="4851c-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="4851c-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)