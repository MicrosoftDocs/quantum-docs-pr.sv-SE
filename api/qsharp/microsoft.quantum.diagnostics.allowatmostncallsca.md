---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853539"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="5fc23-102">AllowAtMostNCallsCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5fc23-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="5fc23-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5fc23-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5fc23-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5fc23-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5fc23-105">Mellan ett anrop till den här åtgärden och dess intilliggande, förutsätter att en viss åtgärd anropas högst ett visst antal gånger.</span><span class="sxs-lookup"><span data-stu-id="5fc23-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="5fc23-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5fc23-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="5fc23-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5fc23-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5fc23-108">Det maximala antalet gånger som `op` kan anropas.</span><span class="sxs-lookup"><span data-stu-id="5fc23-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="5fc23-109">OP: ' TInput => ' TOutput är just + CTL</span><span class="sxs-lookup"><span data-stu-id="5fc23-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="5fc23-110">En åtgärd vars anrop ska begränsas.</span><span class="sxs-lookup"><span data-stu-id="5fc23-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="5fc23-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="5fc23-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="5fc23-112">Ett meddelande som ska visas vid fel.</span><span class="sxs-lookup"><span data-stu-id="5fc23-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5fc23-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fc23-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5fc23-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="5fc23-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="5fc23-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="5fc23-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="5fc23-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="5fc23-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="5fc23-117">Exempel</span><span class="sxs-lookup"><span data-stu-id="5fc23-117">Example</span></span>

<span data-ttu-id="5fc23-118">Följande fragment fungerar inte när de körs på datorer som har stöd för den här diagnostiken:</span><span class="sxs-lookup"><span data-stu-id="5fc23-118">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="5fc23-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5fc23-119">Remarks</span></span>

<span data-ttu-id="5fc23-120">Den här åtgärden kan ersättas av en no-op på mål som inte stöder den.</span><span class="sxs-lookup"><span data-stu-id="5fc23-120">This operation may be replaced by a no-op on targets which do not support it.</span></span>