---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLEA
title: ApplyLEOperationOnPhaseLEA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLEA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 2d5b5ba1a2e8410b46997b2f0dd9764b6ba89cf3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843784"
---
# <a name="applyleoperationonphaselea-operation"></a><span data-ttu-id="661a9-102">ApplyLEOperationOnPhaseLEA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="661a9-102">ApplyLEOperationOnPhaseLEA operation</span></span>

<span data-ttu-id="661a9-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="661a9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="661a9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="661a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="661a9-105">Tillämpar en åtgärd som tar ett <xref:microsoft.quantum.arithmetic.phaselittleendian> register som inloggat på ett mål register av typen <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="661a9-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="661a9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="661a9-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="661a9-107">OP: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  rejust</span><span class="sxs-lookup"><span data-stu-id="661a9-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="661a9-108">Åtgärden som ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="661a9-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="661a9-109">mål: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="661a9-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="661a9-110">Registret som åtgärden tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="661a9-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="661a9-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="661a9-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="661a9-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="661a9-112">Remarks</span></span>

<span data-ttu-id="661a9-113">Registret omvandlas till `LittleEndian` genom att använda <xref:microsoft.quantum.canon.qftle> och returneras sedan till dess ursprungliga representation efter tillämpning av `op` .</span><span class="sxs-lookup"><span data-stu-id="661a9-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="661a9-114">Se även</span><span class="sxs-lookup"><span data-stu-id="661a9-114">See Also</span></span>

- [<span data-ttu-id="661a9-115">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="661a9-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="661a9-116">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="661a9-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [<span data-ttu-id="661a9-117">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="661a9-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)