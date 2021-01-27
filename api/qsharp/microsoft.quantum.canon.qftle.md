---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 893366833e5bd6b358884c11f4534609efd72d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852280"
---
# <a name="qftle-operation"></a><span data-ttu-id="cceb6-102">QFTLE-åtgärd</span><span class="sxs-lookup"><span data-stu-id="cceb6-102">QFTLE operation</span></span>

<span data-ttu-id="cceb6-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cceb6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cceb6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cceb6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cceb6-105">Utför Quantum Fourier-transformeringen på ett Quantum-register som innehåller ett heltal i den lilla endian-representationen.</span><span class="sxs-lookup"><span data-stu-id="cceb6-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cceb6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="cceb6-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="cceb6-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cceb6-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cceb6-108">Quantum register till vilken Quantum Fourier-transformeringen används</span><span class="sxs-lookup"><span data-stu-id="cceb6-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="cceb6-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cceb6-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cceb6-110">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="cceb6-110">Remarks</span></span>

<span data-ttu-id="cceb6-111">Indata och utdata antas vara i little endian kodning.</span><span class="sxs-lookup"><span data-stu-id="cceb6-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="cceb6-112">Se även</span><span class="sxs-lookup"><span data-stu-id="cceb6-112">See Also</span></span>

- [<span data-ttu-id="cceb6-113">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="cceb6-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)