---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: f28f74d34fb4688739646da3dc12ae6734eb4ad4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728473"
---
# <a name="qftle-operation"></a><span data-ttu-id="b1e1c-102">QFTLE-åtgärd</span><span class="sxs-lookup"><span data-stu-id="b1e1c-102">QFTLE operation</span></span>

<span data-ttu-id="b1e1c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b1e1c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b1e1c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b1e1c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b1e1c-105">Utför Quantum Fourier-transformeringen på ett Quantum-register som innehåller ett heltal i den lilla endian-representationen.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="b1e1c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b1e1c-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="b1e1c-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b1e1c-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b1e1c-108">Quantum register till vilken Quantum Fourier-transformeringen används</span><span class="sxs-lookup"><span data-stu-id="b1e1c-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1e1c-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1e1c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b1e1c-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b1e1c-110">Remarks</span></span>

<span data-ttu-id="b1e1c-111">Indata och utdata antas vara i little endian kodning.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1e1c-112">Se även</span><span class="sxs-lookup"><span data-stu-id="b1e1c-112">See Also</span></span>

- [<span data-ttu-id="b1e1c-113">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="b1e1c-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)