---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 7caf33e33318bb74cb160436940eff9f0f2782cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202574"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="78556-102">AllowAtMostNCallsCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="78556-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="78556-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="78556-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="78556-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78556-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78556-105">Mellan ett anrop till den här åtgärden och dess intilliggande, förutsätter att en viss åtgärd anropas högst ett visst antal gånger.</span><span class="sxs-lookup"><span data-stu-id="78556-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="78556-106">Indata</span><span class="sxs-lookup"><span data-stu-id="78556-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="78556-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="78556-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="78556-108">Det maximala antalet gånger som `op` kan anropas.</span><span class="sxs-lookup"><span data-stu-id="78556-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="78556-109">OP: ' TInput => ' TOutput är just + CTL</span><span class="sxs-lookup"><span data-stu-id="78556-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="78556-110">En åtgärd vars anrop ska begränsas.</span><span class="sxs-lookup"><span data-stu-id="78556-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="78556-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="78556-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="78556-112">Ett meddelande som ska visas vid fel.</span><span class="sxs-lookup"><span data-stu-id="78556-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78556-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78556-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="78556-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="78556-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="78556-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="78556-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="78556-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="78556-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="78556-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="78556-117">Remarks</span></span>

<span data-ttu-id="78556-118">Den här åtgärden kan ersättas av en no-op på mål som inte stöder den.</span><span class="sxs-lookup"><span data-stu-id="78556-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>