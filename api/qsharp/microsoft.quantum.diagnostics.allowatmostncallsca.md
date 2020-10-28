---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727369"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="a82ec-102">AllowAtMostNCallsCA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a82ec-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="a82ec-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a82ec-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a82ec-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a82ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a82ec-105">Mellan ett anrop till den här åtgärden och dess intilliggande, förutsätter att en viss åtgärd anropas högst ett visst antal gånger.</span><span class="sxs-lookup"><span data-stu-id="a82ec-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a82ec-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a82ec-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="a82ec-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a82ec-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a82ec-108">Det maximala antalet gånger som `op` kan anropas.</span><span class="sxs-lookup"><span data-stu-id="a82ec-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput-adj--ctl"></a><span data-ttu-id="a82ec-109">OP: ' TInput => ' TOutput just + CTL</span><span class="sxs-lookup"><span data-stu-id="a82ec-109">op : 'TInput => 'TOutput Adj + Ctl</span></span>

<span data-ttu-id="a82ec-110">En åtgärd vars anrop ska begränsas.</span><span class="sxs-lookup"><span data-stu-id="a82ec-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="a82ec-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a82ec-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a82ec-112">Ett meddelande som ska visas vid fel.</span><span class="sxs-lookup"><span data-stu-id="a82ec-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a82ec-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a82ec-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a82ec-114">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="a82ec-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="a82ec-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="a82ec-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="a82ec-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="a82ec-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="a82ec-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a82ec-117">Remarks</span></span>

<span data-ttu-id="a82ec-118">Den här åtgärden kan ersättas av en no-op på mål som inte stöder den.</span><span class="sxs-lookup"><span data-stu-id="a82ec-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>